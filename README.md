# 🚀 Zed Editor Builder

Automated Windows builds of the [Zed editor](https://github.com/zed-industries/zed) using GitHub Actions.

[![Build Status](https://github.com/0xLordGoku/zed-windows-build/actions/workflows/ci.yml/badge.svg)](https://github.com/0xLordGoku/zed-windows-build/actions/workflows/ci.yml)
[![Latest Release](https://img.shields.io/github/v/release/0xLordGoku/zed-windows-build?label=latest%20build)](https://github.com/0xLordGoku/zed-windows-build/releases/latest)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

## 📋 Overview

This repository automatically builds Windows binaries of Zed Editor from source. Each successful build is published as a GitHub Release with the compiled `zed.exe` ready to download.

## ✨ Features

- 🔄 **Automated Builds** - Triggered on push or manual workflow dispatch
- 🎯 **Configurable Targets** - Build from any branch, tag, or commit
- 📦 **GitHub Releases** - Direct download links for all builds
- ⏱️ **Build Tracking** - Duration, size, and version info for each build
- 🪟 **Windows Native** - Optimized for Windows platform

## 📥 Download

Get the latest build from the [Releases page](https://github.com/0xLordGoku/zed-windows-build/releases/latest).

Each release includes:
- `zed-{version}-{commit}.exe` - The Zed editor executable
- Build metadata (version, commit hash, build duration, file size)

## ⚙️ Configuration

The build configuration is set in the workflow file (`.github/workflows/ci.yml`):

```yaml
env:
  BUILD_TARGET: "v0.206.0-pre"   # Branch name, tag name, or commit hash
  BUILD_TYPE: "tag"               # "branch" or "tag"
```

### Building Different Versions

**To build from a tag:**
```yaml
BUILD_TARGET: "v0.206.0-pre"
BUILD_TYPE: "tag"
```

**To build from a branch:**
```yaml
BUILD_TARGET: "main"
BUILD_TYPE: "branch"
```

**To build from a specific commit:**
```yaml
BUILD_TARGET: "abc1234"
BUILD_TYPE: "branch"
```

## 🔧 How It Works

1. **Setup** - Configures Windows environment with long path support
2. **Install Dependencies** - CMake and Rust toolchain via Chocolatey
3. **Clone Repository** - Fetches Zed source code from GitHub
4. **Checkout Target** - Switches to specified branch/tag/commit
5. **Build** - Compiles release binary using `cargo build --release`
6. **Publish** - Creates GitHub Release with the compiled executable

## 🚀 Triggering a Build

### Automatic
Builds trigger automatically on every push to the repository.

### Manual
1. Go to the [Actions tab](https://github.com/0xLordGoku/zed-windows-build/actions)
2. Select the "CI" workflow
3. Click "Run workflow"
4. Choose the branch and click "Run workflow"

## 📊 Build Information

Each release includes:
- **Version** - Zed version from Cargo.toml or git tag
- **Target** - The branch/tag/commit that was built
- **Commit Hash** - Short commit hash for traceability
- **Build Duration** - How long the build took
- **File Size** - Size of the compiled executable

## 🛠️ Requirements

The workflow uses:
- **GitHub Actions** - `windows-latest` runner
- **Chocolatey** - For installing CMake and Rust
- **Git** - For cloning and version control
- **Cargo** - Rust build system

## 📝 License

This build automation repository is provided as-is. Zed Editor itself is licensed under its own terms - see the [Zed repository](https://github.com/zed-industries/zed) for details.

## 🤝 Contributing

Feel free to:
- Report issues with the build process
- Suggest improvements to the workflow
- Request specific Zed versions to build

## 📌 Notes

- Builds are marked as releases (not pre-releases)
- Each build creates a unique tag with timestamp
- Build logs are available in the Actions tab
- Windows Defender may flag the executable initially (false positive)

## 🔗 Links

- [Zed Editor Official Repository](https://github.com/zed-industries/zed)
- [Zed Editor Website](https://zed.dev)
- [Build Workflow](.github/workflows/ci.yml)
- [Latest Release](https://github.com/0xLordGoku/zed-windows-build/releases/latest)

---

**Note:** This is an unofficial build repository. For official Zed releases, visit [zed.dev](https://zed.dev).
