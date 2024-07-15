# Usage

## Inputs

```yaml
save-path:
  required: true
  description: The path (including the filename) to save the downloaded asset to.
owner:
  required: true
  description: The owner of the repository.
repo:
  required: true
  description: The repository name.
token:
  required: true
  default: ${{ github.token }}
  description: The GitHub token used to authenticate. Must have the content:read permission for private repositories.
asset-name-pattern:
  required: true
  description: A regular expression pattern to match the asset name. The match must be unique.
```

## Example

```yaml
steps:
  - uses: OptimalCNC/download_from_latest_release@v1
    with:
      save-path: "neovim.appimage.zsync.sha256sum"
      owner: "neovim"
      repo: "neovim"
      asset-name-pattern: ".*.zsync\\.sha256sum"
```
