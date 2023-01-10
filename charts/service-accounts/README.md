# iam-service-account

![Version: 0.1.9](https://img.shields.io/badge/Version-0.1.9-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.1.9](https://img.shields.io/badge/AppVersion-0.1.9-informational?style=flat-square)

A Helm Chart for creating GCP service accounts and assigning roles

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Gabriel Garoz | <gab.120gg@gmail.com> |  |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| global.folderId | string | `nil` |  |
| global.projectId | string | `nil` |  |
| principals | string | `nil` |  |

## Example usage
```Chart.yaml```
```yaml
apiVersion: v2
name: my-service-account
type: application
version: 1.0.0

dependencies:
  - name: name: gcp-service-accounts
    version: "0.1.1"
    repository: ""
```
Service account without roles assignment

```values.yaml```
```yaml
global:
  projectId: my-project-123

serviceAccounts:
  test-service-account:
    create: true
    displayName: Test service account
```
Service accounts with roles assignment

```values.yaml```
```yaml
global:
  projectId: my-project-123
  projectId: my-folder-321

serviceAccounts:
  argocd:
    create: true
    displayName: Argo CD service account
    projectRoles:
      - container.developer
      - gkehub.gatewayReader
  admin:
    create: false
    folderRoles:
      - resourcemanager.projectCreator
```