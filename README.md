<!--
SPDX-FileCopyrightText: The dolt-installer Authors
SPDX-License-Identifier: 0BSD
 -->

# dolt-installer GitHub Action

This action installs [dolt](https://github.com/dolthub/dolt) into the `PATH` of a GitHub Actions runner.

## Usage

This action supports GitHub-provided Linux, macOS and Windows runners. Self-hosted runners are not tested and may not
work correctly. In order to use this action in your workflow, add the following snippet to the YAML file of the workflow:

```yaml
uses: sebhoss/dolt-installer@v1
with:
  version: latest # optional
```

Example using a specific version of `dolt`:

```yaml
jobs:
  dolt-action:
    name: Install and verify Dolt
    steps:
      - name: Install Dolt
        uses: sebhoss/dolt-installer@v1
        with:
          version: '0.40.32'
      - name: Verify Dolt Installation
        run: dolt version
```

### Optional Inputs
The following optional inputs:

| Input               | Description                                                            |
|---------------------|------------------------------------------------------------------------|
| `version`           | `dolt` version to use. Defaults to `latest`.                           |
| `install-directory` | Installation directory for `dolt` binaries. Defaults to `$HOME/.dolt`. |
