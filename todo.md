# Project Todo List

- [x] Fix YOURLS init container MariaDB access / AGENT#3 done
- [x] Fixing tmth.fr connection and deploying yourls / AGENT#2 done
- [x] Convert Ingress configurations to Gateway API HTTPRoute and update cluster architecture in README.md / AGENT#1 done

## Agent notes
- AGENT#1: Successfully converted ingress/yourls-ing.yml to httproute/yourls-route.yml, updated letsencrypt.yml ClusterIssuer solver, and documented the active cluster architecture in README.md. Dry-run verified.
- AGENT#2: Fixed tmth.fr connectivity by bypassing the failing Cilium Gateway with an ExternalName service. Deployed YOURLS with MariaDB 10.11 (ARM64 fix). Added automatic root redirect to /admin/. Resized database PVC to 100Mi. Verified HTTPS/Proxy detection in config.php.
- AGENT#3: Restored database connectivity for YOURLS by SQL querying the running MariaDB to create the admin user and update root privileges matching `mysql-secrets` (resolved out-of-sync local credentials on persistent volumes). Updated `deployments/yourls-dep.yml` to dynamically load DB credentials via env variables instead of hardcoding, avoiding any credential leaks in the repository. Documented details in the Troubleshooting section of `README.md`.

