# setup-copilot

A GitHub Action to install the [GitHub Copilot CLI](https://github.com/github/copilot-cli) in your workflow.

## Usage

```yaml
steps:
  - uses: actions/setup-copilot@v1
    with:
      version: "latest" # optional, defaults to "latest"
      github-token: ${{ secrets.COPILOT_TOKEN }} # optional, defaults to github.token
  - run: copilot --version
```

## Inputs

| Input          | Description                                       | Required | Default          |
| -------------- | ------------------------------------------------- | -------- | ---------------- |
| `version`      | Version to install (`latest`, `prerelease`, or a specific version like `1.0.0`) | No | `latest` |
| `github-token` | GitHub token for Copilot authentication           | No       | `github.token`   |

## Outputs

| Output    | Description                            |
| --------- | -------------------------------------- |
| `version` | The version of Copilot CLI installed   |

## Examples

### Install latest version

```yaml
- uses: actions/setup-copilot@v1
```

### Install a specific version

```yaml
- uses: actions/setup-copilot@v1
  with:
    version: "1.2.3"
```

### Use with a custom token

```yaml
- uses: actions/setup-copilot@v1
  with:
    github-token: ${{ secrets.COPILOT_TOKEN }}
```

## How it works

This action uses the [official Copilot CLI install script](https://gh.io/copilot-install) to download and install the binary, with checksum verification. The binary is installed to the runner's tool cache and added to `PATH`.

## License

[MIT](LICENSE)
