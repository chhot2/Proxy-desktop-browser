# Building for Windows

## Prerequisites

1. Install [Rust](https://rustup.rs/)
2. Install [Node.js](https://nodejs.org/) (v20 or later)
3. Install [Bun](https://bun.sh/) (recommended) or use npm
4. Install Visual Studio Build Tools with C++ workload

## Build Steps

### 1. Clone the repository

git clone https://github.com/Cicdsd/Proxy-desktop-browser.git
cd Proxy-desktop-browser

### 2. Install frontend dependencies

cd ui-tauri
bun install
# or: npm install

### 3. Build the frontend

bun run build
# or: npm run build

### 4. Build the Tauri desktop application

bun run tauri:build
# or: npm run tauri:build

The built executable will be in ui-tauri/src-tauri/target/release/bundle/.

## Pre-built Binaries

Pre-built Windows binaries are available in the [Releases](https://github.com/Cicdsd/Proxy-desktop-browser/releases) section.

## GitHub Actions Build

The Windows build is automatically triggered via GitHub Actions on every push to the main branch. The workflow file is located at .github/workflows/build-windows.yml.

## Cross-compilation from Linux

To cross-compile for Windows from Linux:

1. Install MinGW-w64: sudo apt-get install mingw-w64
2. Add the Windows target: rustup target add x86_64-pc-windows-gnu
3. Build: cargo build --target x86_64-pc-windows-gnu --release

Note: Cross-compilation may not include all Tauri features. For full builds, use Windows or GitHub Actions.
