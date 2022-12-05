# gke-standard

![Version: 0.3.0](https://img.shields.io/badge/Version-0.3.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.3.0](https://img.shields.io/badge/AppVersion-0.3.0-informational?style=flat-square)

A Helm Chart for provisioning a GKE Standard Cluster

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Gabriel Garoz | <gab.120gg@gmail.com> |  |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| cluster.addonsConfig | object | See each add-on default value | GKE add-ons configuration |
| cluster.clusterSecondaryRangeName | string | `"pods"` | Private IP range name for pods to use, this range must already exist |
| cluster.location | string | `"us-central1"` | Compute location (region for a regional cluster or zone for a zonal cluster) |
| cluster.masterAuthorizedNetworksConfig | object | `{"cidrBlock":"0.0.0.0/0","displayName":"Public internet"}` | Master authorized networks |
| cluster.network.isExternal | string | `"false"` | Whether the network reference managed by Config Connector. If managed, set "true". |
| cluster.network.networkRef | string | `"network-regional"` | Reference to the VPC |
| cluster.network.subnetworkRef | string | `"subnet-regional"` | Reference to the subnet |
| cluster.privateClusterConfig.enablePrivateEndpoint | bool | `false` | Whether the cluster endpoint should be private |
| cluster.privateClusterConfig.enablePrivateNodes | bool | `true` | Whether the cluster nodes should be private |
| cluster.privateClusterConfig.masterGlobalAccessConfig | object | `{"enabled":true}` | Enable global access to the GKE control plane's internal loab balancer. |
| cluster.privateClusterConfig.masterIpv4CidrBlock | string | `"10.254.0.0/28"` | Immutable. The IP range in CIDR notation to use for the hosted master network.        |
| cluster.servicesSecondaryRangeName | string | `"services"` | Private IP range name for services to use, this range must already exist |
| cluster.verticalPodAutoscaling.enabled | bool | `true` |  |
| global | object | REQUIRED | The GCP Project ID for this cluster |
| k8sAddons.argocdProject | string | `"default"` |  |
| k8sAddons.enabled | string | `"false"` | Whether to automatically enable K8s addo-ns after cluster creation |
| k8sAddons.namespace | string | `"default"` |  |
| k8sAddons.repoPath | string | `"*"` |  |
| k8sAddons.repoUrl | string | `"required"` |  |
| nodePool.autoscaling.maxNodeCount | int | `3` | Maximum node count |
| nodePool.autoscaling.minNodeCount | int | `2` | Minimum node count |
| nodePool.location | string | `"us-central1"` | Compute location (region for a regional cluster or zone for a zonal cluster) |
| nodePool.name | string | `"custom-nodepool"` | Name of this node pool |
| nodePool.nodeConfig.diskSizeGb | int | `100` |  |
| nodePool.nodeConfig.diskType | string | `"pd-standard"` |  |
| nodePool.nodeConfig.machineType | string | `"n1-standard-2"` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.11.0](https://github.com/norwoodj/helm-docs/releases/v1.11.0)