# SITO

SITO is a JUCE-based audio synthesizer plugin built from the Pamplejuce template. It targets VST3, Standalone, and CLAP formats and is configured to build with CMake.

## Project status

This repository is being prepared for open-source release. The current setup includes:

- CMake build system
- Recursive submodules for JUCE and plugin dependencies
- GitHub Actions CI for build/test across Linux, macOS, and Windows
- Catch2 test support

## Supported output formats

- VST3
- Standalone
- CLAP

## Requirements

- Git 2.39+
- CMake 3.25+
- Ninja (recommended)
- A C++ compiler with C++23 support
- `git submodule` support for fetching JUCE and other dependencies

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
cmake -B Builds -DCMAKE_BUILD_TYPE=Release .
```

3. Build the project:

```bash
cmake --build Builds --config Release
```

4. Run tests:

```bash
ctest --test-dir Builds --verbose --output-on-failure
```

## GitHub Actions

This repository includes a cross-platform CI workflow at `.github/workflows/build_and_test.yml`.
It builds, tests, and validates the project on Linux, macOS, and Windows.

## Notes

- The plugin uses JUCE and `clap-juce-extensions` as submodules.
- Packaging and notarization are not required for open-source source validation.
- If you want release artifacts, configure signing secrets and update the workflow accordingly.

## Contributing

See `CONTRIBUTING.md` for contribution guidelines.
