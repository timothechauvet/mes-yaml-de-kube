# Mes .YAML de Kubernetes ☸️

> *Sanitized, public Kubernetes manifests for my Oracle OCI bare-metal-ish cluster (Jodukube). Secret values are stripped.*

![Kubernetes](https://img.shields.io/badge/-Kubernetes-blue.svg) ![Oracle OCI](https://img.shields.io/badge/-Oracle%20OCI-blue.svg) ![GitOps](https://img.shields.io/badge/-GitOps-blue.svg) ![Gateway API](https://img.shields.io/badge/-Gateway%20API-blue.svg)

## 🏗️ Architecture
Declarative GitOps repository utilizing Kubernetes Gateway API. Deployed on Oracle Cloud Infrastructure.

## Repository Structure 📁
```
.
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
```

## Kubernetes Resources 🚀
- **ConfigMap** : Configuration data for applications
- **Deployments** : Application deployment specifications
- **HTTPRoute** : Gateway API routing configurations
- **Services** : Internal and external network exposure


## 💻 Tech Stack
- **Kubernetes**
- **YAML**
- **Gateway API**
- **MetalLB**


---
*Generated with care by Homardless 🦞*
