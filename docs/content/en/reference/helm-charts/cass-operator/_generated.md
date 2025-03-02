

![Version: 0.33.0](https://img.shields.io/badge/Version-0.33.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.9.0](https://img.shields.io/badge/AppVersion-1.9.0-informational?style=flat-square)

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Cass Operator Team | cass-operator@datastax.com | https://github.com/k8ssandra/cass-operator |
| K8ssandra Team | k8ssandra-developers@googlegroups.com | https://github.com/k8ssandra |

## Source Code

* <https://github.com/k8ssandra/cass-operator>
* <https://github.com/k8ssandra/k8ssandra/tree/main/charts/cass-operator>

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| file://../k8ssandra-common | k8ssandra-common | 0.28.4 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| global.clusterScoped | bool | `false` | Determines whether cass-operator only watch and manages CassandraDatacenters in the same namespace in which the operator is deployed or if watches and manages CassandraDatacenters across all namespaces. |
| nameOverride | string | `""` | A name in place of the chart name which is used in the metadata.name of objects created by this chart. |
| fullnameOverride | string | `""` | A name in place of the value used for metadata.name in objects created by this chart. The default value has the form releaseName-chartName. |
| commonLabels | object | `{}` | Labels to be added to all deployed resources. |
| replicaCount | int | `1` | Sets the number of cass-operator pods. |
| admissionWebhooks | object | `{"enabled":false}` | Configures admission webhooks deployed with cass-operator. |
| admissionWebhooks.enabled | bool | `false` | Turns the admission webhooks on or off |
| image.registry | string | `"docker.io"` | Container registry containing the repository where the image resides |
| image.repository | string | `"k8ssandra/cass-operator"` | Docker repository for cass-operator |
| image.pullPolicy | string | `"IfNotPresent"` | Pull policy for the operator container |
| image.tag | string | `"v1.9.0"` | Tag of the cass-operator image to pull from image.repository |
| image.registryOverride | string | `nil` | Docker registry containing all cass-operator related images. Setting this allows for usage of an internal registry without specifying serverImage, configBuilderImage, and busyboxImage on all CassandraDatacenter objects. |
| imagePullSecrets | list | `[]` | References to secrets to use when pulling images. See: https://kubernetes.io/docs/tasks/configure-pod-container/pull-image-private-registry/ |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account. |
| podAnnotations | object | `{}` | Annotations for the cass-operator pod. |
| podSecurityContext | object | `{}` | PodSecurityContext for the cass-operator pod. See: https://kubernetes.io/docs/tasks/configure-pod-container/security-context/ |
| securityContext.runAsNonRoot | bool | `true` | Run cass-operator container as non-root user |
| securityContext.runAsGroup | int | `65534` | Group for the user running the cass-operator container / process |
| securityContext.runAsUser | int | `65534` | User for running the cass-operator container / process |
| securityContext.readOnlyRootFilesystem | bool | `true` | Run cass-operator container having read-only root file system permissions. |
| resources | object | `{}` | Resources requests and limits for the cass-operator pod. We usually recommend not to specify default resources and to leave this as a conscious choice for the user. This also increases chances charts run on environments with little resources, such as Minikube. If you want to specify resources, add `requests` and `limits` for `cpu` and `memory` while removing the existing `{}` |
| vmwarePSPEnabled | bool | `false` | Enables specific VMware functionality. If you need this functionality it will automatically be enabled for you. |
