# Mes .YAML de Kubernetes ☸️

Collection of my .yml scripts for my personal Kube cluster (consisting currently of 1 VM 🤓🤓)

![GitHub last commit (branch)](https://img.shields.io/github/last-commit/timothechauvet/mes-yaml-de-kube/main)

## What's this 🤓

Kubernetes
YAML

This repository contains YAML configurations for Kubernetes deployments and Kind (Kubernetes in Docker) clusters.

## Repository Structure 📁

```
.
├── deployments/
│   └── ... (Kubernetes deployment YAML files)
├── kind/
│   └── ... (Kind cluster configuration YAML files)
└── README.md
```

## Kube Deployments 🚀

The `deployments/` directory contains Kubernetes deployment configurations. 

## Kind Configurations 🐳

The `kind/` directory houses configuration files for Kind clusters. 

## Usage 🛠️

To use these configurations:

1. Clone this repository:
   ```
   git clone https://github.com/timothechauvet/mes-yaml-de-kube.git
   ```

2. Navigate to the desired directory:
   ```
   cd mes-yaml-de-kube/deployments
   ```
   or
   ```
   cd mes-yaml-de-kube/kind
   ```

3. Apply the configurations using `kubectl` or `kind`:
   ```
   kubectl apply -f your-deployment.yaml
   ```
   or
   ```
   kind create cluster --config your-kind-config.yaml
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