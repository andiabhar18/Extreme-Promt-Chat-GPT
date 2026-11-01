# MarkItDown integration notes

## 1. Upstream project and inspected source snapshot

- Project: Microsoft MarkItDown
- Source repository: https://github.com/microsoft/markitdown
- Purpose: convert files to Markdown for LLM and text-analysis workflows.
- Uploaded source snapshot inspected for this plugin update: `markitdown` version `0.1.9`; `markitdown-mcp` version `0.0.1a8`.
- License in the supplied source: MIT. This plugin references the upstream project and does not bundle or claim ownership of its implementation.

The uploaded repository documents support for PDF, PowerPoint, Word, Excel, images, audio, HTML, text-based formats such as CSV/JSON/XML, ZIP archives, YouTube URLs, EPUB, and other formats. Actual format support depends on the installed MarkItDown version and optional dependencies. Do not assume every converter is present in every installation.

## 2. MCP interface documented in the supplied source

The supplied `markitdown-mcp` package exposes one MCP tool:

- `convert_to_markdown(uri: string)` — converts a resource described by an `http:`, `https:`, `file:`, or `data:` URI to Markdown.

The package documents STDIO as its default transport and optional Streamable HTTP/SSE operation. Its HTTP server defaults to `127.0.0.1` on port `3001`.

## 3. Critical security limitation

The upstream MCP README explicitly describes the server as intended for local use with trusted agents. It does not provide authentication. It runs with the privileges of its process and can read files or network resources accessible to that process. The upstream guidance warns against binding it to non-localhost interfaces without understanding the security implications.

Therefore:

- Do not expose an unmodified MarkItDown MCP server as a public remote endpoint.
- Do not invent a remote MCP URL or claim this plugin is connected to one.
- Do not grant a converter unrestricted filesystem or network access.
- A remote deployment would need authentication, authorization, upload-only or allowlisted resource access, sandboxing, file-size/type limits, timeouts, rate limits, temporary-file cleanup, SSRF protections, and logging that avoids recording sensitive document contents.
- Do not process confidential files through optional cloud OCR or Azure services without the user's informed authorization.

## 4. Local setup reference (not a ChatGPT cloud connection)

The upstream README documents local installation with:

```bash
pip install markitdown-mcp
```

The default local STDIO server command is:

```bash
markitdown-mcp
```

For local Streamable HTTP/SSE testing, the upstream README documents:

```bash
markitdown-mcp --http --host 127.0.0.1 --port 3001
```

The documented local Streamable HTTP endpoint is `http://127.0.0.1:3001/mcp`. Keep the host bound to localhost for local use. This local process is not automatically reachable from ChatGPT web/mobile or from a cloud-hosted private plugin. A host-specific MCP connection must be configured and tested separately.

## 5. Optional OCR and cloud services

The supplied repository includes an optional `markitdown-ocr` package. Its README says it adds LLM-vision OCR for images embedded in PDF, DOCX, PPTX, and XLSX, and requires a configured `llm_client` and `llm_model`. Without those, its OCR is skipped and the standard converter is used.

The repository also documents optional Azure Document Intelligence and Azure Content Understanding integrations. These are separately configured services; some operations can incur charges and send document content to external services. Do not activate them by default.

## 6. Operational rule for this plugin

This plugin release implements the decision policy and workflow for MarkItDown-first content ingestion. It does not package the Python runtime, deploy a server, or establish a live MCP connection. It may call MarkItDown only when a compatible converter is actually available in the active host. Otherwise, use the host's native file-reading capabilities and accurately disclose the fallback when material.
