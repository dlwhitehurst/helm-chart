mariadb
=======
Fast, reliable, scalable, and easy to use open-source relational database system. MariaDB Server is intended for mission-critical, heavy-load production systems as well as for embedding into mass-deployed software. Highly available MariaDB cluster.

Current chart version is `0.1.0`

Source code can be found [here](https://mariadb.org)


## Chart Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| db.forcePassword | bool | `false` |  |
| db.name | string | `"my_database"` |  |
| db.password | string | `nil` |  |
| db.user | string | `nil` |  |
| image.debug | bool | `false` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.registry | string | `"docker.io"` |  |
| image.repository | string | `"bitnami/mariadb"` |  |
| image.tag | string | `"10.3.18-debian-9-r36"` |  |
| master.affinity | object | `{}` |  |
| master.antiAffinity | string | `"soft"` |  |
| master.config | string | `"[mysqld]\nskip-name-resolve\nexplicit_defaults_for_timestamp\nbasedir=/opt/bitnami/mariadb\nplugin_dir=/opt/bitnami/mariadb/plugin\nport=3306\nsocket=/opt/bitnami/mariadb/tmp/mysql.sock\ntmpdir=/opt/bitnami/mariadb/tmp\nmax_allowed_packet=16M\nbind-address=0.0.0.0\npid-file=/opt/bitnami/mariadb/tmp/mysqld.pid\nlog-error=/opt/bitnami/mariadb/logs/mysqld.log\ncharacter-set-server=UTF8\ncollation-server=utf8_general_ci\n\n[client]\nport=3306\nsocket=/opt/bitnami/mariadb/tmp/mysql.sock\ndefault-character-set=UTF8\nplugin_dir=/opt/bitnami/mariadb/plugin\n\n[manager]\nport=3306\nsocket=/opt/bitnami/mariadb/tmp/mysql.sock\npid-file=/opt/bitnami/mariadb/tmp/mysqld.pid"` |  |
| master.extraInitContainers | string | `""` |  |
| master.livenessProbe.enabled | bool | `true` |  |
| master.livenessProbe.failureThreshold | int | `3` |  |
| master.livenessProbe.initialDelaySeconds | int | `120` |  |
| master.livenessProbe.periodSeconds | int | `10` |  |
| master.livenessProbe.successThreshold | int | `1` |  |
| master.livenessProbe.timeoutSeconds | int | `1` |  |
| master.nodeSelector | object | `{}` |  |
| master.persistence.accessModes[0] | string | `"ReadWriteOnce"` |  |
| master.persistence.annotations | object | `{}` |  |
| master.persistence.enabled | bool | `true` |  |
| master.persistence.mountPath | string | `"/bitnami/mariadb"` |  |
| master.persistence.size | string | `"8Gi"` |  |
| master.podDisruptionBudget.enabled | bool | `false` |  |
| master.podDisruptionBudget.minAvailable | int | `1` |  |
| master.readinessProbe.enabled | bool | `true` |  |
| master.readinessProbe.failureThreshold | int | `3` |  |
| master.readinessProbe.initialDelaySeconds | int | `30` |  |
| master.readinessProbe.periodSeconds | int | `10` |  |
| master.readinessProbe.successThreshold | int | `1` |  |
| master.readinessProbe.timeoutSeconds | int | `1` |  |
| master.resources | object | `{}` |  |
| master.service.annotations | object | `{}` |  |
| master.tolerations | list | `[]` |  |
| master.updateStrategy.type | string | `"RollingUpdate"` |  |
| metrics.annotations."prometheus.io/port" | string | `"9104"` |  |
| metrics.annotations."prometheus.io/scrape" | string | `"true"` |  |
| metrics.enabled | bool | `false` |  |
| metrics.extraArgs.master | list | `[]` |  |
| metrics.extraArgs.slave | list | `[]` |  |
| metrics.image.pullPolicy | string | `"IfNotPresent"` |  |
| metrics.image.registry | string | `"docker.io"` |  |
| metrics.image.repository | string | `"bitnami/mysqld-exporter"` |  |
| metrics.image.tag | string | `"0.12.1-debian-9-r75"` |  |
| metrics.livenessProbe.enabled | bool | `true` |  |
| metrics.livenessProbe.failureThreshold | int | `3` |  |
| metrics.livenessProbe.initialDelaySeconds | int | `120` |  |
| metrics.livenessProbe.periodSeconds | int | `10` |  |
| metrics.livenessProbe.successThreshold | int | `1` |  |
| metrics.livenessProbe.timeoutSeconds | int | `1` |  |
| metrics.readinessProbe.enabled | bool | `true` |  |
| metrics.readinessProbe.failureThreshold | int | `3` |  |
| metrics.readinessProbe.initialDelaySeconds | int | `30` |  |
| metrics.readinessProbe.periodSeconds | int | `10` |  |
| metrics.readinessProbe.successThreshold | int | `1` |  |
| metrics.readinessProbe.timeoutSeconds | int | `1` |  |
| metrics.resources | object | `{}` |  |
| metrics.serviceMonitor.enabled | bool | `false` |  |
| metrics.serviceMonitor.selector.prometheus | string | `"kube-prometheus"` |  |
| rbac.create | bool | `false` |  |
| replication.enabled | bool | `true` |  |
| replication.forcePassword | bool | `false` |  |
| replication.password | string | `nil` |  |
| replication.user | string | `"replicator"` |  |
| rootUser.forcePassword | bool | `false` |  |
| rootUser.password | string | `nil` |  |
| securityContext.enabled | bool | `true` |  |
| securityContext.fsGroup | int | `1001` |  |
| securityContext.runAsUser | int | `1001` |  |
| service.port | int | `3306` |  |
| service.type | string | `"ClusterIP"` |  |
| serviceAccount.create | bool | `false` |  |
| slave.affinity | object | `{}` |  |
| slave.antiAffinity | string | `"soft"` |  |
| slave.config | string | `"[mysqld]\nskip-name-resolve\nexplicit_defaults_for_timestamp\nbasedir=/opt/bitnami/mariadb\nport=3306\nsocket=/opt/bitnami/mariadb/tmp/mysql.sock\ntmpdir=/opt/bitnami/mariadb/tmp\nmax_allowed_packet=16M\nbind-address=0.0.0.0\npid-file=/opt/bitnami/mariadb/tmp/mysqld.pid\nlog-error=/opt/bitnami/mariadb/logs/mysqld.log\ncharacter-set-server=UTF8\ncollation-server=utf8_general_ci\n\n[client]\nport=3306\nsocket=/opt/bitnami/mariadb/tmp/mysql.sock\ndefault-character-set=UTF8\n\n[manager]\nport=3306\nsocket=/opt/bitnami/mariadb/tmp/mysql.sock\npid-file=/opt/bitnami/mariadb/tmp/mysqld.pid"` |  |
| slave.extraInitContainers | string | `""` |  |
| slave.livenessProbe.enabled | bool | `true` |  |
| slave.livenessProbe.failureThreshold | int | `3` |  |
| slave.livenessProbe.initialDelaySeconds | int | `120` |  |
| slave.livenessProbe.periodSeconds | int | `10` |  |
| slave.livenessProbe.successThreshold | int | `1` |  |
| slave.livenessProbe.timeoutSeconds | int | `1` |  |
| slave.nodeSelector | object | `{}` |  |
| slave.persistence.accessModes[0] | string | `"ReadWriteOnce"` |  |
| slave.persistence.annotations | string | `nil` |  |
| slave.persistence.enabled | bool | `true` |  |
| slave.persistence.size | string | `"8Gi"` |  |
| slave.podDisruptionBudget.enabled | bool | `false` |  |
| slave.podDisruptionBudget.minAvailable | int | `1` |  |
| slave.readinessProbe.enabled | bool | `true` |  |
| slave.readinessProbe.failureThreshold | int | `3` |  |
| slave.readinessProbe.initialDelaySeconds | int | `45` |  |
| slave.readinessProbe.periodSeconds | int | `10` |  |
| slave.readinessProbe.successThreshold | int | `1` |  |
| slave.readinessProbe.timeoutSeconds | int | `1` |  |
| slave.replicas | int | `1` |  |
| slave.resources | object | `{}` |  |
| slave.service.annotations | object | `{}` |  |
| slave.tolerations | list | `[]` |  |
| slave.updateStrategy.type | string | `"RollingUpdate"` |  |
| volumePermissions.enabled | bool | `false` |  |
| volumePermissions.image.pullPolicy | string | `"Always"` |  |
| volumePermissions.image.registry | string | `"docker.io"` |  |
| volumePermissions.image.repository | string | `"bitnami/minideb"` |  |
| volumePermissions.image.tag | string | `"stretch"` |  |
| volumePermissions.resources | object | `{}` |  |
