# Windows Build Instructions

## Prerequisites

1. Windows 10/11 or Windows Server 2019+
2. Rust toolchain - Install from https://rustup.rs
3. Node.js 18+ - Install from https://nodejs.org
4. Bun - Install from https://bun.sh
5. Visual Studio Build Tools - Required for Windows builds

## Building on Windows

1. Clone the repository
2. cd ui-tauri && bun install
3. bun run build
4. cd src-tauri && cargo tauri build

The built executable will be in ui-tauri/src-tauri/target/release/bundle/

## GitHub Actions

This repository includes a GitHub Actions workflow that automatically builds Windows executables on push.

## Current Build Status

- Linux build: Working
- Code compilation: Clean (zero warnings)  
- Tests: 93 tests passing
- Windows build: Requires Windows environment or GitHub Actions
