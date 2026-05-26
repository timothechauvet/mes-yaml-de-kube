# Mes .YAML de Kubernetes ☸️

Collection of my .yml scripts for my personal Kube cluster (consisting currently of 1 VM 🤓🤓)

![GitHub last commit (branch)](https://img.shields.io/github/last-commit/timothechauvet/mes-yaml-de-kube/main)

## What's this 🤓

Kubernetes
YAML

This repository contains YAML configurations for Kubernetes deployments and my K3s cluster.

## Repository Structure 📁

```
.
├── certificate/
│   └── ... (TLS certificate configurations)
├── clusterissuer/
│   └── ... (Cert-manager cluster issuer configurations)
├── configmap/
│   └── ... (ConfigMap resources)
├── deployments/
│   └── ... (Kubernetes deployment configurations)
├── httproute/
│   └── ... (Gateway API HTTPRoute configurations)
├── metallb/
│   └── ... (MetalLB load balancer configurations)
├── pv/
│   └── ... (Persistent Volume definitions)
├── pvc/
│   └── ... (Persistent Volume Claims)
├── secrets/
│   └── ... (Secret resources)
├── services/
│   └── ... (Service configurations)
└── README.md
```

## Kubernetes Resources 🚀

- **Certificate** : SSL/TLS certificate configurations
- **ClusterIssuer** : Cert-manager configurations for automated certificate management
- **ConfigMap** : Configuration data for applications
- **Deployments** : Application deployment specifications
- **HTTPRoute** : External access routing via Gateway API
- **MetalLB** : Bare metal load balancer setup
- **PV/PVC** : Storage configurations
- **Secrets** : Sensitive data management
- **Services** : Internal networking configurations

## Cluster Architecture & Components ☸️

The personal Kube cluster runs the following stack of core and infrastructure components:

| Component | Image | Description |
| :--- | :--- | :--- |
| **ArgoCD** | `quay.io/argoproj/argocd:v3.2.0` | GitOps Continuous Delivery toolset |
| **Dex** | `ghcr.io/dexidp/dex:v2.43.0` | Federated OpenID Connect provider (used by ArgoCD) |
| **Redis** | `public.ecr.aws/docker/library/redis:8.2.2-alpine` | Key-value store cache (used by ArgoCD) |
| **Cilium CNI & Gateway API** | `quay.io/cilium/cilium:v1.18.3` | EBPF-based networking, security, and Gateway API controller |
| **Cilium Operator** | `quay.io/cilium/operator-generic:v1.18.3` | Cilium cluster administration operator |
| **Cilium Envoy** | `quay.io/cilium/cilium-envoy:v1.34.10-1761014632-c360e8557eb41011dfb5210f8fb53f` | Envoy proxy for Cilium Gateway API L7 routing |
| **Cloudflared** | `cloudflare/cloudflared:latest` | Cloudflare Tunnel agent for secure external access |
| **Nginx** | `nginx:alpine` | Standalone Nginx web server instance |
| **CoreDNS** | `registry.k8s.io/coredns/coredns:v1.11.1` | Cluster DNS resolution |
| **Metrics Server** | `registry.k8s.io/metrics-server/metrics-server:v0.8.0` | Resource usage metrics collector |
| **Kube API Server** | `registry.k8s.io/kube-apiserver:v1.34.1` | Kubernetes control plane API server |
| **Kube Controller Manager** | `registry.k8s.io/kube-controller-manager:v1.34.1` | Kubernetes control plane controller loop manager |
| **Kube Scheduler** | `registry.k8s.io/kube-scheduler:v1.34.1` | Kubernetes control plane scheduler |
| **Etcd** | `registry.k8s.io/etcd:3.6.4-0` | Kubernetes control plane distributed database |

## Usage 🛠️

To use these configurations:

1. Clone this repository:
   ```
   git clone https://github.com/timothechauvet/mes-yaml-de-kube.git
   ```

2. Navigate to the desired directory:
   ```
   cd mes-yaml-de-kube/something
   ```

3. Apply the configurations using `kubectl` or `kind`:
   ```
   kubectl apply -f your-deployment.yaml
   ```

## Contributing 🤝

Don't contribute thx

## License 📄

Not needed

## Did I use a GenAI for this poorly written readme ? 🤖

Yes

## Contact 🤗
- via Mastodon : https://h4.io/@timothechauvet
- via LinkedIn : https://www.linkedin.com/in/timothechauvet/
- via Twitter : https://twitter.com/timothechauvet
- via Mail : timothe@chauvet.cloud
- or via an issue in this repository

## Donations 💸
Either ask me for a job with a higher salary, or go to your local subway and give some poor person something like 2€. I'd be happy to know about that.