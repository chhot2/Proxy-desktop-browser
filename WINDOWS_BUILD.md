# Windows Build Instructions

## Prerequisites

1. Windows 10/11 or Windows Server 2019+
2. Rust toolchain - Install from https://rustup.rs
3. Node.js 18+ - Install from https://nodejs.org
4. Bun - Install from https://bun.sh
5. Visual Studio Build Tools - Required for Windows builds

## Pre-built Windows Executables

Pre-built Windows executables are available in the [GitHub Releases](https://github.com/Cicdsd/Proxy-desktop-browser/releases):

- **virtual-ip-browser.exe** - Main Windows desktop application
- **api-server.exe** - API server component

### System Requirements
- Windows 10 or later
- WebView2 Runtime (usually pre-installed on Windows 10/11)

## Building on Windows

1. Clone the repository
2. cd ui-tauri && bun install
3. bun run build
4. cd src-tauri && cargo tauri build

The built executable will be in ui-tauri/src-tauri/target/release/bundle/

## Cross-compiling from Linux

To cross-compile for Windows from Linux: