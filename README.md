# Helm Charts Catalog

DevSecOps HQ Lab Helm Chart Repository. This repository hosts standalone CustomResourceDefinition (CRD) and utility Helm charts distributed via both a classic Helm repository and GitHub Container Registry (OCI).

## Available Charts

| Chart | Version | App Version | Description |
| --- | --- | --- | --- |


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
