# tpl

![Version: 2.1.1](https://img.shields.io/badge/Version-2.1.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.23.0](https://img.shields.io/badge/AppVersion-1.23.0-informational?style=flat-square)

A Helm chart for Kubernetes

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| ConfigMap | object | `{}` | Using ConfigMap it is not necessary to create volumes, only for the main container |
| CronJobs | list | `[]` | Create cronjobs |
| Secrets | object | `{}` | Using Secrets there is no need to create volumes in the main container only |
| Strategy | object | `{"rollingUpdate":{"maxSurge":1,"maxUnavailable":0},"type":"RollingUpdate"}` | Deployment strategy |
| UpdateStrategy | object | `{"type":"RollingUpdate"}` | Statefulset strategy |
| UpdateStrategy.type | string | `"RollingUpdate"` | OnDelete  |
| affinity | object | `{}` | Affinity settings for pod assignment |
| args | list | `[]` | Define additional args if command is used |
| autoscaling | object | `{"behavior":{},"enabled":false,"maxReplicas":10,"minReplicas":1}` | HPA settings |
| command | list | `[]` | Define command to be executed by grafana container at startup |
| configMounts | list | `[]` | Need to use ConfigMap without creating volume only main container |
| containerPorts | list | `[{"containerPort":80,"name":"http","protocol":"TCP"}]` | Additional Container Ports |
| envFrom | list | `[]` | Allows you to load environment variables from kubernetes secret or config map |
| extraConfigMap | object | `{"enabled":false}` | Allows you to load environment variables from kubernetes secret or config map from envFrom, extraInitContainers and extraContainers |
| extraContainers | list | `[]` | Sidecar containers to add to the pod |
| extraEnvs | list | `[]` | Extra environment variables passed to pods |
| extraInitContainers | list | `[]` | Additional init containers ref: https://kubernetes.io/docs/concepts/workloads/pods/init-containers/  |
| extraSecrets | object | `{"enabled":false}` | Allows you to load environment variables from kubernetes secret or config map from envFrom, extraInitContainers and extraContainers |
| extraVolumeMounts | list | `[]` | Additional volume mounts |
| extraVolumes | list | `[]` | Additional volumes |
| image.pullPolicy | string | `"IfNotPresent"` | Image pull policy  |
| image.registry | string | `"docker.io"` | The Docker registry |
| image.repository | string | `"nginx"` | Docker image repository |
| image.tag | string | `""` | Overrides the image tag whose default is the chart appVersion. |
| imagePullSecrets | list | `[]` | Image pull secrets |
| ingress.annotations | string | `nil` | Ingress annotations |
| ingress.enabled | bool | `false` | Enable Ingress |
| ingress.hosts | list | `[{"host":"example.domain.io","paths":[{"number":80,"path":"/","pathType":"Prefix"}]}]` | Ingress accepted hostnames   |
| ingress.ingressClassName | string | `""` | Ingress Class Name. MAY be required for Kubernetes versions >= 1.18 |
| ingress.tls | list | `[]` | Ingress TLS configuration            |
| labels | object | `{}` | Deployment and Statefulset labels |
| nodeSelector | object | `{}` | Node labels for pod assignment |
| persistence | object | `{"enabled":false,"volumeClaimTemplates":[{"accessModes":["ReadWriteOnce"],"name":"data","resources":{"requests":{"storage":"1Gi"}}}]}` | Persistence only type statefulset |
| podAnnotations | object | `{}` | Pod annotations |
| podLabels | object | `{}` | Pod labels |
| podSecurityContext | object | `{}` | Pod securityContext |
| probe | object | `{}` | Liveness and Readiness Probe settings |
| replicaCount | int | `1` |  |
| resources | object | `{}` | CPU/Memory resource requests/limits |
| secretMounts | list | `[]` | Need to use Secrets without the need to create volume only main container |
| secretsProvider | object | `{"data":[],"enabled":false,"name":"secret-name","objects":[],"provider":"aws","region":"us-east-1"}` | Secret store CSI Driver - https://secrets-store-csi-driver.sigs.k8s.io/ |
| securityContext | object | `{"privileged":false}` | Deployment securityContext |
| service.annotations | object | `{}` | Service annotations |
| service.labels | object | `{}` | Custom service labels |
| service.servicePorts | list | `[{"name":"http","port":80,"targetPort":80}]` | Kubernetes port where service is exposed |
| service.type | string | `"ClusterIP"` | Kubernetes service type |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| serviceAccount.create | bool | `false` | Specifies whether a service account should be created |
| serviceAccount.name | string | `"secret-sa"` | If not set and create is true, a name is generated using the fullname template |
| serviceMonitor | object | `{"annotations":{},"create":false,"endpoints":[],"jobLabel":"","labels":{}}` | Metrics Service Monitor |
| serviceMonitor.annotations | object | `{}` | Service Monitor annotations |
| serviceMonitor.create | bool | `false` | Specifies whether a service monitor should be created |
| serviceMonitor.endpoints | list | `[]` | endpoints Service monitor |
| serviceMonitor.jobLabel | string | `""` | jobLabel Service monitor |
| serviceMonitor.labels | object | `{}` | Additional labels Service monitor |
| statefulset | bool | `false` | Type Statefulset  |
| tolerations | list | `[]` | Toleration labels for pod assignment |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.11.0](https://github.com/norwoodj/helm-docs/releases/v1.11.0)
