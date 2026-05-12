# Contributing to SITO

Thank you for your interest in contributing to SITO. This project uses CMake and Git submodules, so please follow these guidelines.

## Filing issues

- Use the issue templates provided in `.github/ISSUE_TEMPLATE/`.
- Provide a short description of the problem, reproduction steps, and expected behavior.

## Pull requests

- Open a pull request against the `main` branch.
- Include a clear summary of the changes.
- Reference any related issues.
- Keep PRs small and focused.

## Development workflow

1. Pull the latest changes:

```bash
git checkout main
git pull --rebase origin main
```

2. Update submodules:

```bash
git submodule update --init --recursive
```

3. Build and test locally:

```bash
cmake -B Builds -DCMAKE_BUILD_TYPE=Debug .
cmake --build Builds --config Debug
ctest --test-dir Builds --verbose --output-on-failure
```

4. Run code formatting checks with `clang-format` if applicable.

## Coding style

- Follow the existing JUCE and project coding style.
- Use descriptive variable and function names.
- Keep changes small and easy to review.

## License

By contributing, you agree that your contributions are released under the project MIT license.
