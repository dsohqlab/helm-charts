# Helm Charts Catalog

DevSecOps HQ Lab Helm Chart Repository. This repository hosts standalone CustomResourceDefinition (CRD) and utility Helm charts distributed via both a classic Helm repository and GitHub Container Registry (OCI).

## Available Charts

| Chart | Version | App Version | Description |
| --- | --- | --- | --- |
| `aws-load-balancer-controller-crds` | `3.6.2` | `3.6.2` | A Helm chart to install the CustomResourceDefinitions for AWS Load Balancer Controller |
| `cert-manager-crds` | `1.21.3` | `1.21.3` | A Helm chart to install the CustomResourceDefinitions for cert-manager (certificates, issuers, ACME orders and challenges) |
| `cilium-crds` | `1.20.4` | `1.20.4` | A Helm chart to install the CustomResourceDefinitions for Cilium (cilium.io v2 and v2alpha1) |
| `external-dns-crds` | `0.24.0` | `0.24.0` | A Helm chart to install the CustomResourceDefinitions for ExternalDNS (DNSEndpoint, DNSRecord) |
| `external-secrets-crds` | `2.14.0` | `2.14.0` | A Helm chart to install the CustomResourceDefinitions for External Secrets Operator (stores, external/push secrets, generators) |
| `external-snapshotter-crds` | `8.7.0` | `8.7.0` | A Helm chart to install the CustomResourceDefinitions for the Kubernetes CSI external-snapshotter (VolumeSnapshot and VolumeGroupSnapshot APIs) |
| `gateway-api-crds` | `1.7.0` | `1.7.0` | A Helm chart to install the CustomResourceDefinitions for Kubernetes Gateway API, standard channel |
| `gateway-api-exp-crds` | `1.7.0` | `1.7.0` | A Helm chart to install the CustomResourceDefinitions for Kubernetes Gateway API, experimental channel |
| `kyverno-crds` | `1.19.2` | `1.19.2` | A Helm chart to install the CustomResourceDefinitions for Kyverno (policies, CEL policies, exceptions, policy reports) |
| `secrets-store-csi-driver-crds` | `1.6.1` | `1.6.1` | A Helm chart to install the CustomResourceDefinitions for Secrets Store CSI driver for Kubernetes secrets |
| `traefik-crds` | `3.7.17` | `3.7.17` | A Helm chart to install the CustomResourceDefinitions for Traefik Proxy (IngressRoutes, Middlewares, TLS options, transports) |
| `vertical-pod-autoscaler-crds` | `1.8.1` | `1.8.1` | A Helm chart to install the CustomResourceDefinitions for the Kubernetes Vertical Pod Autoscaler (VerticalPodAutoscaler, checkpoints) |

## Usage

Charts are distributed in two ways:

1. **[Classic Helm Repository](https://helm.sh/docs/topics/chart_repository/)** via GitHub Pages
2. **[OCI Registry](https://helm.sh/docs/topics/registries/)** via GitHub Container Registry (ghcr.io)

---

### Method 1: Installing from the Helm Repository

Add the repository to Helm:

```bash
helm repo add dsohqlab https://dsohqlab.github.io/helm-charts
helm repo update
```

Install or upgrade a chart:

```bash
helm upgrade --install <release-name> dsohqlab/<chart-name> --version <version>
```

---

### Method 2: Installing from OCI Registry (Helm 3.8+)

All charts are pushed to the GitHub Container Registry under `ghcr.io/dsohqlab/helm-charts`.

Install directly from OCI:

```bash
helm upgrade --install <release-name> oci://ghcr.io/dsohqlab/helm-charts/<chart-name> --version <version>
```

---

### Uninstalling a Chart

To remove an installed release:

```bash
helm uninstall <release-name>
```

> [!NOTE]
> For CRD charts, removing the chart may retain or delete custom resource definitions depending on the `keepOnUninstall` value setting. Check the documentation in each chart directory for details.
