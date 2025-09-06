# Helm Charts

A collection of Helm charts that configure Kubernetes Config Connector (KCC) resources for Google Cloud Platform (GCP) infrastructure provisioning and management.

These charts deploy Kubernetes Custom Resource Definitions (CRDs) that enable you to manage GCP resources declaratively through Kubernetes manifests, leveraging Config Connector to automatically provision and manage your cloud infrastructure.

## Prerequisites

- Kubernetes cluster with Config Connector installed
- Proper GCP service account credentials configured
- Required GCP APIs enabled

## Available Charts

| Chart | Description | Version |
|-------|-------------|---------|
| `apis` | Enable GCP API services | 0.1.4 |
| `cluster-registration` | Register clusters with GKE Hub | 0.1.2 |
| `gcs-buckets` | Provision Google Cloud Storage buckets | 0.1.0 |
| `gke-autopilot` | Provision GKE Autopilot clusters | 0.1.9 |
| `gke-nodepool` | Manage GKE node pools | 0.2.1 |
| `gke-standard` | Provision GKE Standard clusters | 0.3.9 |
| `iam-service-accounts` | Create GCP service accounts and assign roles | 0.1.9 |
| `k8s-addons` | Deploy Kubernetes addons | 0.1.0 |
| `service-accounts` | Create GCP service accounts | 0.1.9 |
| `vpc-subnet` | Provision VPC with subnets | 0.1.4 |

## Usage

Each chart can be installed independently:

```bash
helm install <chart-name> ./charts/<chart-name>
```

## Maintainer

Gabriel Garoz
