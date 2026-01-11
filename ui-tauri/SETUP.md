# Virtual IP Browser - Setup and Run Guide

## Quick Start

This application has been fixed to resolve the white screen issue. Follow these steps to run the app:

### Prerequisites

1. **Node.js** (v18 or higher) - [Download](https://nodejs.org/)
2. **Rust** (for Tauri) - [Install](https://www.rust-lang.org/tools/install)
3. **System Dependencies** (platform-specific):
   - **Linux**: `webkit2gtk`, `libgtk-3-dev`
   - **macOS**: Xcode Command Line Tools
   - **Windows**: WebView2 (usually pre-installed)

### Installation Steps

1. **Navigate to the UI directory**:
   ```bash
   cd ui-tauri
   ```

2. **Install dependencies**:
   ```bash
   npm install --legacy-peer-deps
   ```

3. **Build the frontend**:
   ```bash
   npm run build
   ```

4. **Run the application**:
   ```bash
   npm run tauri dev
   ```

## What Was Fixed

The white screen issue was caused by:

1. **Missing dependencies** - `node_modules` was not installed
2. **Svelte 5 syntax errors** - Fixed incorrect usage of `$derived` and `$effect` runes
3. **Build configuration** - Updated package.json to use npm instead of bun

### Changes Made:

1. **BrowserShell.svelte**:
   - Fixed `$derived` syntax (removed function call syntax)
   - Fixed `$effect` syntax
   - Updated all references to `activeTab` to use the value directly instead of calling it as a function
   - Added proper null checks using optional chaining

2. **package.json**:
   - Changed build commands from `bunx --bun vite` to `vite`
   - Updated all scripts to use npm instead of bun

3. **.gitignore**:
   - Added to prevent committing build artifacts and dependencies

## Development

### Available Scripts

- `npm run dev` - Start Vite development server
- `npm run build` - Build the frontend for production
- `npm run tauri dev` - Run the Tauri app in development mode
- `npm run tauri build` - Build the application for production
- `npm run check` - Run Svelte type checking
- `npm run format` - Format code with Prettier
- `npm run lint` - Lint code with ESLint

## Troubleshooting

### White Screen Issues

If you still see a white screen:

1. **Check the console** (Ctrl+Shift+I or Cmd+Option+I):
   - Look for JavaScript errors
   - Check network tab for failed requests

2. **Verify build output**:
   ```bash
   ls -la dist/
   ```
   You should see `index.html` and `assets/` folder

3. **Clear build cache**:
   ```bash
   rm -rf dist/
   npm run build
   ```

4. **Reinstall dependencies**:
   ```bash
   rm -rf node_modules/
   npm install --legacy-peer-deps
   ```

### Dependency Conflicts

If you encounter peer dependency warnings:
```bash
npm install --legacy-peer-deps
```

This is expected due to Svelte 5 and vite-plugin-svelte version compatibility.

## Features

- **Virtual IP Browsing**: Browse with virtual IP addresses
- **Proxy Support**: Built-in proxy management and rotation
- **Multi-Tab Interface**: Chromium-style tab management
- **Privacy Features**: WebRTC protection, DNS over HTTPS, tracker blocking
- **Bookmarks & History**: Full browsing history and bookmark management

## Architecture

- **Frontend**: Svelte 5 + TypeScript + Vite
- **Backend**: Tauri (Rust)
- **Browser Core**: Custom Rust-based browser engine with proxy support

## License

See LICENSE file in the root directory.
