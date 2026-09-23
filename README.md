# Kestra Deploy Flows Action

Official GitHub Action to create, update, or delete [Flows](https://kestra.io/docs/workflow-components/flow) from a folder recursively, as part of your [CI/CD pipeline](https://kestra.io/docs/version-control-cicd/cicd/github-action).

Split out of [`kestra-io/github-actions`](https://github.com/kestra-io/github-actions) so it can be published standalone on the GitHub Marketplace (marketplace requires 1 repo = 1 action).

## Usage

```yaml
- uses: actions/checkout@v4
- uses: kestra-io/deploy-flows-action@main
  with:
    directory: ./kestra/flows
    server: ${{ secrets.KESTRA_HOSTNAME }}
    override: true
```

## Inputs

| Name | Description | Default |
| --- | --- | --- |
| `directory` | Folder containing your flows | `./` |
| `namespace` | Force a namespace to deploy flows to | - |
| `override` | Override flows if they already exist | `false` |
| `recursive` | Recurse into subdirectories when `directory` is a folder | `true` |
| `failFast` | Stop on the first deployment error | `false` |
| `server` | URL of your Kestra server | required |
| `apiToken` | API Token (EE only) | - |
| `user` / `password` | Basic auth credentials | - |
| `tenant` | Tenant identifier (EE only) | `main` |
| `kestractlVersion` | Version of [kestractl](https://github.com/kestra-io/kestractl) to use | `latest` |

## Links
- Docs: https://kestra.io/docs/how-to-guides/github-actions
- Related actions: [`validate-flows-action`](https://github.com/kestra-io/validate-flows-action), [`deploy-namespace-files-action`](https://github.com/kestra-io/deploy-namespace-files-action)
