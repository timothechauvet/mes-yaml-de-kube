# Project Todo List

- [x] Upgrade YOURLS to 1.10.4 and fix password write permission error / AGENT#3 done
- [x] Deploy jodubranding application stack and configure API Gateway and Cloudflared / AGENT#3 done
- [x] Cleanup unnecessary K3s/cryptobot configurations and update README.md / AGENT#3 done
- [x] Fix YOURLS init container MariaDB access / AGENT#3 done
- [x] Fixing tmth.fr connection and deploying yourls / AGENT#2 done
- [x] Convert Ingress configurations to Gateway API HTTPRoute and update cluster architecture in README.md / AGENT#1 done
- [x] Fix jodubranding HTTPRoute/Gateway 502 bad gateway and synchronize repo files / AGENT#4 done

## Agent notes
- AGENT#1: Successfully converted ingress/yourls-ing.yml to httproute/yourls-route.yml, updated letsencrypt.yml ClusterIssuer solver, and documented the active cluster architecture in README.md. Dry-run verified.
- AGENT#2: Fixed tmth.fr connectivity by bypassing the failing Cilium Gateway with an ExternalName service. Deployed YOURLS with MariaDB 10.11 (ARM64 fix). Added automatic root redirect to /admin/. Resized database PVC to 100Mi. Verified HTTPS/Proxy detection in config.php.
- AGENT#3: Deployed the `choose-your-username` application stack (backend, frontend, Redis, API Gateway, Cloudflared tunnel client) to a new `jodubranding` namespace. Configured Keel auto-updating policy annotations for both frontend and backend. Registered QEMU binfmt interpreters on the host kernel to support running the x86_64 container images on the ARM64 cluster node `o1k2`. Restored database connectivity for YOURLS by SQL querying the running MariaDB to create the admin user and update root privileges matching `mysql-secrets`. Cleaned up cert-manager/Let's Encrypt configurations (not relevant in cloudflared context), removed all obsolete `cryptobot` resources, and updated `README.md` for the Jodukube full Kubernetes migration. Upgraded YOURLS to 1.10.4-apache and added `YOURLS_NO_HASH_PASSWORD` ConfigMap definition to prevent read-only filesystem writes when auto-encrypting plain-text user passwords.
- AGENT#4: Resolved the 502 Bad Gateway by replacing the degraded Cilium Envoy Gateway with a lightweight Nginx reverse proxy running on the control-plane node (o1k2). Verified HTTP 200 routing to frontend and backend services. Synchronized all manifests to the repository after sanitizing username/credentials across secret templates.





