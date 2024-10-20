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
├── ingress/
│   └── ... (Ingress controller configurations)
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
- **Ingress** : External access configurations
- **MetalLB** : Bare metal load balancer setup
- **PV/PVC** : Storage configurations
- **Secrets** : Sensitive data management
- **Services** : Internal networking configurations

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