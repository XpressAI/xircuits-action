# Xircuits Compilation Action

This GitHub Action compiles the given Xircuits files and creates a `requirements.txt` file to run them. 
It supports specifying individual files, glob patterns, or directories to compile.

## Inputs

### `files`

**Description:** List of files to compile (e.g., `"File1.xircuits File2.xircuits foo/bar/baz/File3.xircuits"`).

### `pattern`

**Description:** Glob pattern of files to compile (e.g., `"*.xircuits"`).

### `directories`

**Description:** Directories containing Xircuits files to compile (e.g., `"xai_components/xai_custom other_dir"`).

### `xircuits_version`

**Required:** No  
**Default:** Latest version  
**Description:** Xircuits version to use for compilation (e.g., `"==1.10.1"`).

## Usage

To use this action, you can include it in your GitHub Actions workflow file:

```yaml
steps:
  - uses: actions/checkout@v4
  - uses: xpressai/xircuits-action@main
    with:
      files: 'my_file.xircuits'
      xircuits_version: '==1.10.1'
```

This action will:

1. Collect the specified Xircuits files.
2. Set up Python and create a virtual environment.
3. Install the specified version of Xircuits (or the latest version if not specified).
4. Compile the collected Xircuits files.
5. Collect and compile the dependencies from all compiled files into a top-level `requirements.txt` file.

The compiled Python files and the `requirements.txt` file will be available in the workspace for further use in the workflow.

## Contributing

If you have suggestions for improving this action, please create an issue or submit a pull request to the [XpressAI/xircuits-action](https://github.com/XpressAI/xircuits-action) repository.
