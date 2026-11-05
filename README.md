# AlonePDF

AlonePDF is an original, local-first PDF editor prototype. Its interface and code are independently designed; Sejda is used only as a high-level reference for common PDF editing workflows.

## Run locally

```powershell
node --version # Node.js 22.13+
npm install
npm run dev
```

Open the local URL printed by Vite, choose a PDF, make edits, and export the result.

## Current editor capabilities

- Open and render PDF files locally in the browser.
- Navigate pages with thumbnails, page controls, and zoom.
- Add and reposition text, signatures, highlights, shapes, whiteout overlays, images, and HTTP(S) links.
- Select PDF text runs with **Edit text**, then visually replace them and export the result. Existing color, serif/sans-serif/monospace family, and bold/italic styles are detected where PDF.js exposes them; use the **Bold** option to adjust bold weight. Replacements with up to three extra characters stay at the original size and extend the line as needed; longer replacements scale down to fit on one line.
- Adjust text, signature, shape, highlight, and link colors; adjust text size.
- Undo and redo edits, then export an edited PDF.
- File contents are not sent to AlonePDF servers.

## Current limitations

Edits are visual overlays. **Edit text** covers the selected words and places replacement text on top; it does not rewrite or remove the original embedded text, which remains in the PDF and may still be recoverable or searchable. This is not secure redaction. Since the original content is retained and overlay data is added, exporting edits (including visually deleting text) can increase file size; this is not secure deletion. Replacement text uses a standard font with the same detected generic family (serif, sans-serif, or monospace); matching a specific embedded font and background remains approximate, particularly on rotated text, colored/image backgrounds, ruled tables, or unusual fonts. Longer replacements may use a smaller font to remain on one line. Scanned pages without selectable text cannot use Edit text; use an OCR workflow or add a text overlay instead. Form fields are not yet editable. Only PNG and JPEG images are accepted. PDF export uses standard fonts for WinAnsi text and bundled Noto Sans fonts for supported Latin and extended Latin characters. Unsupported glyphs produce an explicit export error. The Noto Sans font license is included at `public/font-licenses/NotoSans-OFL.txt`. Protected/complex PDFs may not export. The editor currently does not merge or split documents.

## Development and native analysis

REA and Ghidra are optional development tools, not editor features or runtime dependencies. REA can help inspect a concrete native binary if one is introduced; Ghidra is not a PDF parsing or editing library. Do not use Ghidra to inspect ordinary TypeScript/JavaScript source or the reference website. Ghidra 12.1.x requires a 64-bit Java 21 JDK and is located using `GHIDRA_INSTALL_DIR`.

The project does not embed an REA server or configure the developer's Claude/VS Code client. REA tool availability depends on the active agent session's MCP registration and reconnection. See `CLAUDE.md` for project-specific guidance.

## Validation

```powershell
npm test
npm run build
```
