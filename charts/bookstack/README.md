bookstack
=========
A Helm chart for Kubernetes

This chart is used for the installation and hosting of Bookstack on Kubernetes.
BookStack is a simple, self-hosted, easy-to-use platform for organizing and storing information.

[Overview of Bookstack](https://www.bookstackapp.com/)

Trademarks: This software listing is packaged by David L Whitehurst. Any respective trademarks mentioned in the offering are owned by the respective companies, and use of them does not imply any affiliation or endorsement.
                           
## TL;DR

```bash
$ helm repo add dlwhitehurst https://dlwhitehurst.github.io/helm-charts/
$ helm install bookstack dlwhitehurst/bookstack
```
Current chart version is `0.1.9`

## Chart Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://charts.bitnami.com/bitnami | mariadb | 11.4.2 |

## Chart Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| app.key | string | `nil` |  |
| appurl | string | `"https://bookstack.dlwhitehurst.com"` |  |
| autoscaling.enabled | bool | `false` |  |
| autoscaling.maxReplicas | int | `100` |  |
| autoscaling.minReplicas | int | `1` |  |
| autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| env | object | `{}` |  |
| externalDatabase.database | string | `"bookstack"` |  |
| externalDatabase.host | string | `"mariadb.mariadb.svc.cluster.local"` |  |
| externalDatabase.password | string | `nil` |  |
| externalDatabase.port | int | `3306` |  |
| externalDatabase.user | string | `"bookstack"` |  |
| fullnameOverride | string | `""` |  |
| image.pullPolicy | string | `"Always"` |  |
| image.repository | string | `"solidnerd/bookstack"` |  |
| image.tag | string | `""` |  |
| imagePullSecrets | list | `[]` |  |
| ingress.annotations | object | `{}` |  |
| ingress.className | string | `""` |  |
| ingress.enabled | bool | `false` |  |
| ingress.hosts[0].host | string | `"bookstack-example.local"` |  |
| ingress.hosts[0].paths[0].path | string | `"/"` |  |
| ingress.hosts[0].paths[0].pathType | string | `"ImplementationSpecific"` |  |
| ingress.tls | list | `[]` |  |
| mariadb.db.name | string | `"bookstack"` |  |
| mariadb.db.user | string | `"bookstack"` |  |
| mariadb.enabled | bool | `false` |  |
| mariadb.master.persistence.accessMode | string | `"ReadWriteOnce"` |  |
| mariadb.master.persistence.enabled | bool | `false` |  |
| mariadb.master.persistence.size | string | `"8Gi"` |  |
| mariadb.replication.enabled | bool | `false` |  |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| persistence.storage.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.storage.enabled | bool | `true` |  |
| persistence.storage.size | string | `"8Gi"` |  |
| persistence.uploads.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.uploads.enabled | bool | `true` |  |
| persistence.uploads.size | string | `"8Gi"` |  |
| podAnnotations | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| podSecurityPolicy.enabled | bool | `false` |  |
| rbac.create | bool | `false` |  |
| replicaCount | int | `1` |  |
| resources | object | `{}` |  |
| securityContext | object | `{}` |  |
| service.port | int | `8080` |  |
| service.targetport | int | `8080` |  |
| service.type | string | `"ClusterIP"` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.name | string | `""` |  |
| tolerations | list | `[]` |  |
