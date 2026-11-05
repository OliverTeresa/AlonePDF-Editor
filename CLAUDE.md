# AlonePDF development notes

- The PDF editor is the product's core experience. Preserve the local-first document workflow.
- Treat Sejda as a high-level feature reference only. Do not copy its branding, assets, prose, source, or distinctive design.
- Use REA only when a specific native artifact or runtime question warrants it. Ordinary source inspection does not need REA.
- Ghidra is an optional REA analysis provider for native binaries, not a PDF editing engine. Do not send PDF documents to it or bundle it into the application.
- If native analysis becomes relevant, check that REA tools are actually available in the active Claude Code session. Ghidra is configured through `GHIDRA_INSTALL_DIR`; it needs a 64-bit Java 21 JDK. Do not alter global REA/client settings without the developer's approval.
- Preserve the README's documented limits: existing text replacement, new text, whiteout, and annotations are visual overlays; neither replacement nor whiteout removes the original text; forms and complex document operations are not yet implemented.
- Keep document processing local. Do not add a remote upload path or telemetry without explicit product approval.
