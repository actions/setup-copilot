# setup-copilot

A GitHub Action to install the [GitHub Copilot CLI](https://github.com/github/copilot-cli) in your workflow.

## Usage

```yaml
steps:
  - uses: actions/setup-copilot@v0
    with:
      version: "latest" # optional, defaults to "latest"
      github-token: ${{ secrets.GITHUB_TOKEN }} # optional, defaults to github.token
  - run: copilot --version
```

## Inputs

| Input          | Description                                       | Required | Default          |
| -------------- | ------------------------------------------------- | -------- | ---------------- |
| `version`      | Version to install (`latest`, `prerelease`, or a specific version like `1.0.0`) | No | `latest` |
| `github-token` | GitHub token for downloading Copilot CLI          | No       | `github.token`   |

## Outputs

| Output    | Description                            |
| --------- | -------------------------------------- |
| `version` | The version of Copilot CLI installed   |

## Examples

### Install latest version

```yaml
- uses: actions/setup-copilot@v0
```

### Install a specific version

```yaml
- uses: actions/setup-copilot@v0
  with:
    version: "1.2.3"
```

### Use with a custom token

```yaml
- uses: actions/setup-copilot@v0
  with:
    github-token: ${{ secrets.GH_TOKEN }}
```

## How it works

This action uses the [official Copilot CLI install script](https://gh.io/copilot-install) to download and install the binary, with checksum verification. The binary is installed to the runner's tool cache and added to `PATH`.

## License

[MIT](LICENSE)

## Contributions

Contributions are welcome! See [Contributor's Guide](CONTRIBUTING.md)

## Code of Conduct

:wave: Be nice. See [our code of conduct](CODE_OF_CONDUCT.md)
