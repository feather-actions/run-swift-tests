# Run Swift Tests

This GitHub Action is designed to run Swift tests on your repository. It provides options to enable code coverage and generate a Markdown file from the test results (using [Testify](https://github.com/BinaryBirds/Testify.git) ), which will be displayed in the workflow summary.

## Usage

Include the action in your workflow (make sure that a Swift 5.6+ toolchain is on your PATH, on macOS this should be given, but on Linux you may need to first install it e.g. using [`setup-swift`](https://github.com/fwal/setup-swift)):

```yaml
- uses: feather-actions/run-swift-tests@0.0.1
```
Full example:

```yaml
on: [push]

jobs:
  job-name:
    runs-on: macos-latest

    steps:
      - name: Checkout
        uses: actions/checkout@v4
        with:
          fetch-depth: 1
  
      - name: Run Swift Tests
        uses: feather-actions/run-swift-tests@0.0.1
        with:
          code-coverage: true
          use-testify: true
```

## Inputs

These are the optional inputs of the action:

```yaml
code-coverage: boolean input to enable code coverage
use-testify: boolean input to generate an MD file from the test results and show it in the workflow summary
```