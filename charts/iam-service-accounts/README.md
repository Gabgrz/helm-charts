# iam-service-accounts

![Version: 0.2.0](https://img.shields.io/badge/Version-0.2.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.2.0](https://img.shields.io/badge/AppVersion-0.2.0-informational?style=flat-square)

A Helm Chart for creating GCP service accounts and assigning roles

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Gabriel Garoz | <gab.120gg@gmail.com> |  |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| global.folderId | string; optional | `nil` | Folder ID where service account has permissions over |
| global.projectId | string; required | `nil` | GCP Project ID to create service accounts in |
| principals | map; required | `nil` | Map of principals with optional roles assigned |

## Example usage
```Chart.yaml```
```yaml
apiVersion: v2
name: my-service-account
type: application
version: 1.0.0

dependencies:
  - name: iam-service-account
    version: "0.2.0"
    repository: ""
```
**Service account *without* roles assignment**

```values.yaml```
```yaml
global:
  projectId: my-project-123

principals:
  test-service-account:
    create: true
    displayName: Test service account
```
**Service accounts *with* roles assignment**

```values.yaml```
```yaml
global:
  projectId: my-project-123

principals:
  argocd:
    create: true
    displayName: Argo CD service account
    projectRoles:
      - container.developer
      - gkehub.gatewayReader
  admin:
    create: true
    displayName: Admin editor service account
    projectRoles:
      - editor
```
