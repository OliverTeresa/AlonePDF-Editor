AlonePDF — Local-First PDF Editor & Desktop App
==============================================

AlonePDF is a private, local-first PDF editor. Your files stay entirely on your machine and are never uploaded to any server.

## System Requirements
- Node.js (v18 or higher recommended)
- Windows 10/11 (for the desktop installer) or any modern browser (Chrome, Firefox, Edge)

## Quick Start & Installation Instructions

### 1. Running from Source (Development Mode)
To run the development environment with live reload:
1. Open a terminal in the project directory.
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the Vite development server:
   ```bash
   npm run dev
   ```
4. To run both Vite and the Electron desktop shell concurrently:
   ```bash
   npm run electron:dev
   ```

### 2. Running Tests
To run the test suite (Vitest):
```bash
npm test
```

### 3. Building for Production & Desktop Packaging
- **Web Build Only**:
  ```bash
  npm run build
  ```
- **Build Windows Desktop Installer & Portable EXE**:
  ```bash
  npm run electron:build
  ```
  The generated installers (`alonepdf Setup 0.1.0.exe` and `alonepdf 0.1.0.exe`) will be located in the `dist_electron/` directory (and have also been copied to `C:\Users\RDP\Desktop\AlonePDF-Standalone\`).

## How to Open and Edit a PDF
1. Launch AlonePDF (via browser or desktop EXE).
2. On the home screen, click **"Choose a PDF"** or **drag and drop** a PDF file anywhere onto the window.
3. The PDF loads locally into memory.
4. Select tools from the toolbar to add text, replace text (visual overlay), add whiteouts, or apply annotations/signatures.
5. Click **Export** to save your modified PDF locally.

## Important Architectural Notes & Limitations
- **Local-First**: No telemetry, no remote servers, no data collection. Processing happens entirely in-browser/on-device.
- **Visual Overlays**: Existing text replacement and whiteout annotations are visual overlay masks; neither replacement nor secure-deletion removes the original text streams from the underlying PDF.

