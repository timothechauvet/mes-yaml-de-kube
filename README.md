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

## Cross-tenant node networking
Jodukube currently spans two OCI tenants / VCNs:

- `o1k2` (`lethandrimesnextcloud`) control-plane
- `o2k2` (`tchauvetcoursier`) worker

Both OCI networks use overlapping private CIDR `10.0.0.0/24`. Because of that, direct node-to-node traffic over native private IPs is impossible.

To keep cluster healthy across both nodes, host networking now uses WireGuard underlay between:

- `198.51.100.1` (`o1k2` public IP)
- `198.51.100.2` (`o2k2` public IP)

Host changes applied outside Kubernetes:

- `wg0` WireGuard tunnel on both nodes
- host route override so peer private node IP goes through `wg0`
- iptables accepts traffic from `wg0` and `cilium_wg0`
- OCI security lists allow:
  - `a2k1` admin IP `198.51.100.3/32`
  - inter-node public traffic between `o1k2` and `o2k2`
  - UDP `51820` for host WireGuard

Persistent host service installed on both nodes:

- `wg-quick@wg0.service`
- `jodukube-net.service`

Important: if node IP layout, public IPs, or OCI security lists change, this WireGuard underlay must be updated too.

---
