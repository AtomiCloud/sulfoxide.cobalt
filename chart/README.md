# sulfoxide-cobalt

![Version: 1.14.0](https://img.shields.io/badge/Version-1.14.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: v0.18.2](https://img.shields.io/badge/AppVersion-v0.18.2-informational?style=flat-square)

Helm Chart to install External Secrets, our secret operator, and SecretStore to AtomiCloud's Kubernetes Cluster

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://charts.external-secrets.io | external-secrets | v0.18.2 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| external-secrets | object | `{"certController":{"podAnnotations":{"<<":{"atomi.cloud/layer":"1","atomi.cloud/platform":"sulfoxide","atomi.cloud/service":"chlorine"},"atomi.cloud/module":"cert-controller"},"podLabels":{"<<":{"atomi.cloud/layer":"1","atomi.cloud/platform":"sulfoxide","atomi.cloud/service":"chlorine"},"atomi.cloud/module":"cert-controller"},"podSecurityContext":{"fsGroup":1000,"runAsGroup":1000,"runAsNonRoot":true,"runAsUser":1000},"resources":{"limits":{"cpu":"200m","memory":"256Mi"},"requests":{"cpu":"5m","memory":"128Mi"}},"securityContext":{"allowPrivilegeEscalation":false,"capabilities":{"drop":["ALL"]},"readOnlyRootFilesystem":true,"runAsGroup":1000,"runAsNonRoot":true,"runAsUser":1000},"topologySpreadConstraints":[{"labelSelector":{"matchLabels":{"<<":{"atomi.cloud/layer":"1","atomi.cloud/platform":"sulfoxide","atomi.cloud/service":"chlorine"},"atomi.cloud/module":"cert-controller"}},"maxSkew":1,"topologyKey":"topology.kubernetes.io/zone","whenUnsatisfiable":"ScheduleAnyway"}]},"installCRDs":true,"podAnnotations":{"<<":{"atomi.cloud/layer":"1","atomi.cloud/platform":"sulfoxide","atomi.cloud/service":"chlorine"},"atomi.cloud/module":"operator"},"podLabels":{"<<":{"atomi.cloud/layer":"1","atomi.cloud/platform":"sulfoxide","atomi.cloud/service":"chlorine"},"atomi.cloud/module":"operator"},"podSecurityContext":{"fsGroup":1000,"runAsGroup":1000,"runAsNonRoot":true,"runAsUser":1000},"resources":{"limits":{"cpu":"200m","memory":"256Mi"},"requests":{"cpu":"5m","memory":"64Mi"}},"securityContext":{"allowPrivilegeEscalation":false,"capabilities":{"drop":["ALL"]},"readOnlyRootFilesystem":true,"runAsGroup":1000,"runAsNonRoot":true,"runAsUser":1000},"serviceMonitor":{"enabled":true},"topologySpreadConstraints":[{"labelSelector":{"matchLabels":{"<<":{"atomi.cloud/layer":"1","atomi.cloud/platform":"sulfoxide","atomi.cloud/service":"chlorine"},"atomi.cloud/module":"operator"}},"maxSkew":1,"topologyKey":"topology.kubernetes.io/zone","whenUnsatisfiable":"ScheduleAnyway"}],"webhook":{"podAnnotations":{"<<":{"atomi.cloud/layer":"1","atomi.cloud/platform":"sulfoxide","atomi.cloud/service":"chlorine"},"atomi.cloud/module":"webhook"},"podLabels":{"<<":{"atomi.cloud/layer":"1","atomi.cloud/platform":"sulfoxide","atomi.cloud/service":"chlorine"},"atomi.cloud/module":"webhook"},"podSecurityContext":{"fsGroup":1000,"runAsGroup":1000,"runAsNonRoot":true,"runAsUser":1000},"resources":{"limits":{"cpu":"200m","memory":"256Mi"},"requests":{"cpu":"5m","memory":"64Mi"}},"securityContext":{"allowPrivilegeEscalation":false,"capabilities":{"drop":["ALL"]},"readOnlyRootFilesystem":true,"runAsGroup":1000,"runAsNonRoot":true,"runAsUser":1000},"topologySpreadConstraints":[{"labelSelector":{"matchLabels":{"<<":{"atomi.cloud/layer":"1","atomi.cloud/platform":"sulfoxide","atomi.cloud/service":"chlorine"},"atomi.cloud/module":"webhook"}},"maxSkew":1,"topologyKey":"topology.kubernetes.io/zone","whenUnsatisfiable":"ScheduleAnyway"}]}}` | External Secrets Configuration. See [External Secrets Operator Documentation](https://github.com/external-secrets/external-secrets/tree/main/deploy/charts/external-secrets) |
| podSecurityContext | object | `{"fsGroup":1000,"runAsGroup":1000,"runAsNonRoot":true,"runAsUser":1000}` | YAML Anchor for PodSecurityContext |
| rootToken | object | `{"clientIdKey":"CLIENT_ID","clientSecretKey":"CLIENT_SECRET","create":false,"hostAPI":"https://secrets.atomi.cloud","name":"cobalt-infisical","project":"sulfoxide-sos","secretsPath":"/","type":"infisical","value":""}` | The Root Doppler Token for deploying SecretStore |
| rootToken.clientIdKey | string | `"CLIENT_ID"` | The Kubernetes Secret Key holding the Root Infisical Client ID |
| rootToken.clientSecretKey | string | `"CLIENT_SECRET"` | The Kubernetes Secret Key holding the Root Infisical Client Secret |
| rootToken.create | bool | `false` | To create the secret or use existing secret |
| rootToken.hostAPI | string | `"https://secrets.atomi.cloud"` | The host API of infisical |
| rootToken.name | string | `"cobalt-infisical"` | Name of secret to be created |
| rootToken.project | string | `"sulfoxide-sos"` | Project |
| rootToken.secretsPath | string | `"/"` | The path to the secrets in infisical project |
| rootToken.type | string | `"infisical"` | Type of ClusterSecretStore to be created |
| rootToken.value | string | `""` | The Root Doppler Token Value for deploying SecretStore. This value is sensitive |
| securityContext | object | `{"allowPrivilegeEscalation":false,"capabilities":{"drop":["ALL"]},"readOnlyRootFilesystem":true,"runAsGroup":1000,"runAsNonRoot":true,"runAsUser":1000}` | YAML Anchor for SecurityContext |
| serviceTree | object | `{"layer":"1","platform":"sulfoxide","service":"chlorine"}` | AtomiCloud Service Tree. See [ServiceTree](https://atomicloud.larksuite.com/wiki/OkfJwTXGFiMJkrk6W3RuwRrZs64?theme=DARK&contentTheme=DARK#MHw5d76uDo2tBLx86cduFQMRsBb) |
| storeName | string | `"infisical"` | The name of the doppler ClusterSecretStore that is going to be deployed |
| tags | object | `{"atomi.cloud/layer":"1","atomi.cloud/platform":"sulfoxide","atomi.cloud/service":"chlorine"}` | Kubernetes labels and annotations, following Service Tree |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.14.2](https://github.com/norwoodj/helm-docs/releases/v1.14.2)
