# Run Swift Tests

This GitHub Action checks for local Swift package dependencies in your repository’s Package.swift files. It ensures that no local package references are present.

## Usage

Include the action in your workflow.

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
        uses: feather-actions/run-swift-tests@0.0.2
```

