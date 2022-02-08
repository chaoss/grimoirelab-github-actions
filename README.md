# GrimoireLab GitHub actions

## build

Build a Python package using Poetry and store the package as an artifact for future jobs.

See [build/action.yml](build/action.yml)

### Inputs
- `artifact-name`: artifact name for future jobs (default: artifact).
- `artifact-path`: directory that contains the package to store for future jobs (default: dist).

### Usage

```yaml
steps:
  - uses: chaoss/grimoirelab-github-actions/build@master
    with:
      artifact-name: grimoire-dist
      artifact-path: dist
```


## release

Create a new GitHub release for the repository. 

It uses the tag that triggered the workflow and the notes available under `releases/<tag>.md`.

See [release/action.yml](release/action.yml)

### Inputs
- `github-token`: token provided by actions, read the usage.

### Usage
```yaml
steps:
  - uses: chaoss/grimoirelab-github-actions/release@master
    with:
      github-token: ${{ secrets.GITHUB_TOKEN }}
```
