# SITO
![SITO](assets\images\gh_banner.svg)

![Build & Test](https://github.com/u95/sito/workflows/SITO%20Build%20&%20Test/badge.svg)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Version: 0.0.1](https://img.shields.io/badge/Version-0.0.1-blue.svg)

SITO is a JUCE-based granular synthesizer plugin built from the Pamplejuce template. It targets VST3 and Standalone formats and is configured to build with CMake.

## Table of Contents
### Technical moments
- [Project status](#project-status)
- [Supported output formats](#supported-output-formats)
- [Requirements](#requirements)
- [Quick start](#quick-start)
- [Getting started](#getting-started)
- [GitHub Actions](#github-actions)
- [Notes](#notes)
- [Contributing](#contributing)
### Behind the scenes and my thoughts
- [Backstory](#backstory)
- [Features](#features)
- [Roadmap](#roadmap)

## Project status

This repository is being prepared for open-source release. The current setup includes:

- CMake build system
- Recursive submodules for JUCE and plugin dependencies
- GitHub Actions CI for build/test across Linux, macOS, and Windows
- Catch2 test support

## Supported output formats

- VST3
- Standalone

## Requirements

- Git 2.39+
- CMake 3.25+
- Ninja
- Visual Studio 2022/2026 Build Tools with Desktop development for C++ on Windows, or GCC/Clang on Linux/macOS
- `git submodule` support to fetch JUCE and build dependencies

## Quick start

On Windows, build from an x64 Visual Studio Developer Command Prompt.

```powershell
cd c:\dev\sito
cmake -S . -B build -G Ninja -DCMAKE_BUILD_TYPE=Release
cmake --build build --config Release --target SITO_All
```

This will build both VST3 and Standalone formats.

The release plugin will be written to:

```text
build/SITO_artefacts/Release/VST3/SITO.vst3
```

Run tests with:

```powershell
cmake --build build --config Release --target SITOTests
ctest --test-dir build --verbose
```

## Getting started

1. Clone the repo with submodules:

```bash
git clone --recurse-submodules https://github.com/<your-org>/sito-synthesizer.git
cd sito-synthesizer
```

If you already cloned without submodules:

```bash
git submodule update --init --recursive
```

2. Create a build directory and configure the project:

```bash
cmake -S . -B build -G Ninja -DCMAKE_BUILD_TYPE=Release
```

On Windows, run this from an x64 Visual Studio Developer Command Prompt.

3. Build the plugin:

```bash
cmake --build build --config Release --target SITO_VST3
```

4. Run tests:

```bash
cmake --build build --config Release --target SITOTests
ctest --test-dir build --verbose
```

## GitHub Actions

This repository includes a cross-platform CI workflow at `.github/workflows/build_and_test.yml`.
It builds, tests, and validates the project on Linux, macOS, and Windows.

## Notes

- The plugin uses JUCE as a submodule.
- This repository currently targets VST3 only.
- Packaging and notarization are not required for open-source source validation.
- If you want release artifacts, configure signing secrets and update the workflow accordingly.

## Contributing

See `CONTRIBUTING.md` for contribution guidelines.

## Backstory

## Features

## Roadmap