# gke-nodepool

![Version: 0.1.2](https://img.shields.io/badge/Version-0.1.2-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.1.2](https://img.shields.io/badge/AppVersion-0.1.2-informational?style=flat-square)

A Helm Chart for provisioning GKE Node Pools

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Gabriel Garoz | <gab.120gg@gmail.com> |  |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| nodePool.autoscaling.maxNodeCount | int | `3` | Maximum node count |
| nodePool.autoscaling.minNodeCount | int | `2` | Minimum node count |
| nodePool.location | string | `"us-central1"` | Compute location (region for a regional cluster or zone for a zonal cluster) |
| nodePool.name | string | `"custom-nodepool"` | Name of this node pool |
| nodePool.nodeConfig.diskSizeGb | int | `100` | Disk Size in GB |
| nodePool.nodeConfig.diskType | string | `"pd-standard"` | Disk type |
| nodePool.nodeConfig.machineType | string | `"n1-standard-2"` | Machine type |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.11.0](https://github.com/norwoodj/helm-docs/releases/v1.11.0)
