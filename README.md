<!--
SPDX-FileCopyrightText: The Dolt Installer GitHub Action Authors
SPDX-License-Identifier: 0BSD
 -->

# Dolt Installer GitHub Action

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

## License

```
Permission to use, copy, modify, and/or distribute this software for any
purpose with or without fee is hereby granted.

THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES WITH
REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF MERCHANTABILITY AND
FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY SPECIAL, DIRECT,
INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES WHATSOEVER RESULTING FROM
LOSS OF USE, DATA OR PROFITS, WHETHER IN AN ACTION OF CONTRACT, NEGLIGENCE OR
OTHER TORTIOUS ACTION, ARISING OUT OF OR IN CONNECTION WITH THE USE OR
PERFORMANCE OF THIS SOFTWARE.
```
