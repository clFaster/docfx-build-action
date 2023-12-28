# DocFx Build Action
A GitHub Action to build [Docfx](https://dotnet.github.io/docfx/) documentation.

## Usage
Prerequisites:
- .NET SDK 6.0 or higher
- [clFaster/docfx-setup-action](https://github.com/clFaster/docfx-setup-action)

### Action
- `docfx-file-path`  (optional): Specify this input if your docfx.json is not in the working directory.
- `docfx-output-path`  (optional): Defaults to _site in the folder where the docfx.json file is located.

```yaml
- name: Build Documentation
  uses: clFaster/docfx-build-action@v1
  with:
    docfx-file-path: "docs/docfx.json"
    docfx-output-path: "output-path"
```

### Example Workflow
A complete example of a workflow that builds Docfx documentation.
```yaml
- name: Checkout
  uses: actions/checkout@v4

- name: Setup .NET Core 8.x
  uses: actions/setup-dotnet@v3
  with:
    dotnet-version: "8.x"

- name: Setup DocFx
  uses: clFaster/docfx-setup-action@v1

- name: Build Documentation
  uses: clFaster/docfx-build-action@v1
  with:
    docfx-file-path: "docs/docfx.json"
```