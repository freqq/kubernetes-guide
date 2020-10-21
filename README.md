# Kubernetes Guide

## What is Kubernetes?

Kubernetes is a portable, extensible, open-source platform for managing containerized workloads and services, that facilitates both declarative configuration and automation. It has a large, rapidly growing ecosystem. Kubernetes services, support, and tools are widely available.

The name Kubernetes originates from Greek, meaning helmsman or pilot. Google open-sourced the Kubernetes project in 2014. Kubernetes combines over 15 years of Google's experience running production workloads at scale with best-of-breed ideas and practices from the community.

## **kubectl** - kubernetes command line tool

### Overview

The kubectl command line tool lets you control Kubernetes clusters.

### List of commonly used kubectl commands and flags.

| Operation | Syntax | Description |
|-|-|-|
| alpha | kubectl alpha SUBCOMMAND [flags] | List the available commands that correspond to alpha features, which are not enabled in Kubernetes clusters by default. |
| annotate | kubectl annotate (-f FILENAME \| TYPE NAME \| TYPE/NAME) KEY_1=VAL_1 ... KEY_N=VAL_N [--overwrite] [--all] [--resource-version=version] [flags] | Add or update the annotations of one or more resources. |
| api-resources | kubectl api-resources [flags] | List the API resources that are available. |
| api-versions | kubectl api-versions [flags] | List the API versions that are available. |
| apply | kubectl apply -f FILENAME [flags] | Apply a configuration change to a resource from a file or stdin. |
| attach | kubectl attach POD -c CONTAINER [-i] [-t] [flags] | Attach to a running container either to view the output stream or interact with the container (stdin). |
| auth | kubectl auth [flags] [options] | Inspect authorization. |
| autoscale | kubectl autoscale (-f FILENAME \| TYPE NAME \| TYPE/NAME) [--min=MINPODS] --max=MAXPODS [--cpu-percent=CPU] [flags] | Automatically scale the set of pods that are managed by a replication controller. |
| certificate | kubectl certificate SUBCOMMAND [options] | Modify certificate resources. |
| cluster-info | kubectl cluster-info [flags] | Display endpoint information about the master and services in the cluster. |
| completion | kubectl completion SHELL [options] | Output shell completion code for the specified shell (bash or zsh). |
| config | kubectl config SUBCOMMAND [flags] | Modifies kubeconfig files. See the individual subcommands for details. |
| convert | kubectl convert -f FILENAME [options] | Convert config files between different API versions. Both YAML and JSON formats are accepted. |
| cordon | kubectl cordon NODE [options] | Mark node as unschedulable. |
| cp | kubectl cp <file-spec-src> <file-spec-dest> [options] | Copy files and directories to and from containers. |
| create | kubectl create -f FILENAME [flags] | Create one or more resources from a file or stdin. |
| delete | kubectl delete (-f FILENAME \| TYPE [NAME \| /NAME \| -l label \| --all]) [flags] | Delete resources either from a file, stdin, or specifying label selectors, names, resource selectors, or resources. |
| describe | kubectl describe (-f FILENAME \| TYPE [NAME_PREFIX \| /NAME \| -l label]) [flags] | Display the detailed state of one or more resources. |
| diff | kubectl diff -f FILENAME [flags] | Diff file or stdin against live configuration. |
| drain | kubectl drain NODE [options] | Drain node in preparation for maintenance. |
| edit | kubectl edit (-f FILENAME \| TYPE NAME \| TYPE/NAME) [flags] | Edit and update the definition of one or more resources on the server by using the default editor. |
| exec | kubectl exec POD [-c CONTAINER] [-i] [-t] [flags] [-- COMMAND [args...]] | Execute a command against a container in a pod. |
| explain | kubectl explain [--recursive=false] [flags] | Get documentation of various resources. For instance pods, nodes, services, etc. |
| expose | kubectl expose (-f FILENAME \| TYPE NAME \| TYPE/NAME) [--port=port] [--protocol=TCP\|UDP] [--target-port=number-or-name] [--name=name] [--external-ip=external-ip-of-service] [--type=type] [flags] | Expose a replication controller, service, or pod as a new Kubernetes service. |
| get | kubectl get (-f FILENAME \| TYPE [NAME \| /NAME \| -l label]) [--watch] [--sort-by=FIELD] [[-o \| --output]=OUTPUT_FORMAT] [flags] | List one or more resources. |
| kustomize | kubectl kustomize <dir> [flags] [options] | List a set of API resources generated from instructions in a kustomization.yaml file. The argument must be the path to the directory containing the file, or a git repository URL with a path suffix specifying same with respect to the repository root. |
| label | kubectl label (-f FILENAME \| TYPE NAME \| TYPE/NAME) KEY_1=VAL_1 ... KEY_N=VAL_N [--overwrite] [--all] [--resource-version=version] [flags] | Add or update the labels of one or more resources. |
| logs | kubectl logs POD [-c CONTAINER] [--follow] [flags] | Print the logs for a container in a pod. |
| options | kubectl options | List of global command-line options, which apply to all commands. |
| patch | kubectl patch (-f FILENAME \| TYPE NAME \| TYPE/NAME) --patch PATCH [flags] | Update one or more fields of a resource by using the strategic merge patch process. |
| plugin | kubectl plugin [flags] [options] | Provides utilities for interacting with plugins. |
| port-forward | kubectl port-forward POD [LOCAL_PORT:]REMOTE_PORT [...[LOCAL_PORT_N:]REMOTE_PORT_N] [flags] | Forward one or more local ports to a pod. |
| proxy | kubectl proxy [--port=PORT] [--www=static-dir] [--www-prefix=prefix] [--api-prefix=prefix] [flags] | Run a proxy to the Kubernetes API server. |
| replace | kubectl replace -f FILENAME | Replace a resource from a file or stdin. |
| rollout | kubectl rollout SUBCOMMAND [options] | Manage the rollout of a resource. Valid resource types include: deployments, daemonsets and statefulsets. |
| run | kubectl run NAME --image=image [--env="key=value"] [--port=port] [--dry-run=server\|client\|none] [--overrides=inline-json] [flags] | Run a specified image on the cluster. |
| scale | kubectl scale (-f FILENAME \| TYPE NAME \| TYPE/NAME) --replicas=COUNT [--resource-version=version] [--current-replicas=count] [flags] | Update the size of the specified replication controller. |
| set | kubectl set SUBCOMMAND [options] | Configure application resources. |
| taint | kubectl taint NODE NAME KEY_1=VAL_1:TAINT_EFFECT_1 ... KEY_N=VAL_N:TAINT_EFFECT_N [options] | Update the taints on one or more nodes. |
| top | kubectl top [flags] [options] | Display Resource (CPU/Memory/Storage) usage. |
| uncordon | kubectl uncordon NODE [options] | Mark node as schedulable. |
| version | kubectl version [--client] [flags] | Display the Kubernetes version running on the client and server. |
| wait | kubectl wait ([-f FILENAME] \| resource.group/resource.name \| resource.group [(-l label \| --all)]) [--for=delete\|--for condition=available] [options] | Experimental: Wait for a specific condition on one or many resources. |

### Resource types:

| NAME | SHORTNAMES | APIGROUP | NAMESPACED | KIND |
|-|-|-|-|-|
| bindings |  |  | true | Binding |
| componentstatuses | cs |  | false | ComponentStatus |
| configmaps | cm |  | true | ConfigMap |
| endpoints | ep |  | true | Endpoints |
| events | ev |  | true | Event |
| limitranges | limits |  | true | LimitRange |
| namespaces | ns |  | false | Namespace |
| nodes | no |  | false | Node |
| persistentvolumeclaims | pvc |  | true | PersistentVolumeClaim |
| persistentvolumes | pv |  | false | PersistentVolume |
| pods | po |  | true | Pod |
| podtemplates |  |  | true | PodTemplate |
| replicationcontrollers | rc |  | true | ReplicationController |
| resourcequotas | quota |  | true | ResourceQuota |
| secrets |  |  | true | Secret |
| serviceaccounts | sa |  | true | ServiceAccount |
| services | svc |  | true | Service |
| mutatingwebhookconfigurations |  | admissionregistration.k8s.io | false | MutatingWebhookConfiguration |
| validatingwebhookconfigurations |  | admissionregistration.k8s.io | false | ValidatingWebhookConfiguration |
| customresourcedefinitions | crd,crds | apiextensions.k8s.io | false | CustomResourceDefinition |
| apiservices |  | apiregistration.k8s.io | false | APIService |
| controllerrevisions |  | apps | true | ControllerRevision |
| daemonsets | ds | apps | true | DaemonSet |
| deployments | deploy | apps | true | Deployment |
| replicasets | rs | apps | true | ReplicaSet |
| statefulsets | sts | apps | true | StatefulSet |
| tokenreviews |  | authentication.k8s.io | false | TokenReview |
| localsubjectaccessreviews |  | authorization.k8s.io | true | LocalSubjectAccessReview |
| selfsubjectaccessreviews |  | authorization.k8s.io | false | SelfSubjectAccessReview |
| selfsubjectrulesreviews |  | authorization.k8s.io | false | SelfSubjectRulesReview |
| subjectaccessreviews |  | authorization.k8s.io | false | SubjectAccessReview |
| horizontalpodautoscalers | hpa | autoscaling | true | HorizontalPodAutoscaler |
| cronjobs | cj | batch | true | CronJob |
| jobs |  | batch | true | Job |
| certificatesigningrequests | csr | certificates.k8s.io | false | CertificateSigningRequest |
| leases |  | coordination.k8s.io | true | Lease |
| endpointslices |  | discovery.k8s.io | true | EndpointSlice |
| events | ev | events.k8s.io | true | Event |
| ingresses | ing | extensions | true | Ingress |
| flowschemas |  | flowcontrol.apiserver.k8s.io | false | FlowSchema |
| prioritylevelconfigurations |  | flowcontrol.apiserver.k8s.io | false | PriorityLevelConfiguration |
| ingressclasses |  | networking.k8s.io | false | IngressClass |
| ingresses | ing | networking.k8s.io | true | Ingress |
| networkpolicies | netpol | networking.k8s.io | true | NetworkPolicy |
| runtimeclasses |  | node.k8s.io | false | RuntimeClass |
| poddisruptionbudgets | pdb | policy | true | PodDisruptionBudget |
| podsecuritypolicies | psp | policy | false | PodSecurityPolicy |
| clusterrolebindings |  | rbac.authorization.k8s.io | false | ClusterRoleBinding |
| clusterroles |  | rbac.authorization.k8s.io | false | ClusterRole |
| rolebindings |  | rbac.authorization.k8s.io | true | RoleBinding |
| roles |  | rbac.authorization.k8s.io | true | Role |
| priorityclasses | pc | scheduling.k8s.io | false | PriorityClass |
| csidrivers |  | storage.k8s.io | false | CSIDriver |
| csinodes |  | storage.k8s.io | false | CSINode |
| storageclasses | sc | storage.k8s.io | false | StorageClass |
| volumeattachments |  | storage.k8s.io | false | VolumeAttachment |

### Formatting output:
| Output format | Description |
|-|-|
| -o=custom-columns=<spec> | Print a table using a comma separated list of custom columns |
| -o=custom-columns-file=<filename> | Print a table using the custom columns template in the <filename> file |
| -o=json | Output a JSON formatted API object |
| -o=jsonpath=<templatename> | Print the fields defined in a jsonpath expression |
| -o=jsonpath-file=<filename> | Print the fields defined by the jsonpath expression in the <filename> file |
| -o=name | Print only the resource name and nothing else |
| -o=wide | Output in the plain-text format with any additional information, and for pods, the node name is included |
| -o=yaml | Output a YAML formatted API object |

## Rest

1. Kubernetes:
   1. Cluster architecture:
      1. Nodes
   2. Resources:
      1. Basic:
         1. Pod
         2. Namespace
      2. Workload:
         1. Deployment
         2. ReplicaSet
         3. StatefulSet
         4. DeamonSet
      3. Jobs:
         1. Job
         2. CronJob
      4. Storage:
         1. PersistentVolume
         2. PersistentVolumeClaim
         3. StorageClass
      5. Config:
         1. Secret
         2. ConfigMap
      6. Networking:
         1. Service
         2. Ingress / Ingress Controller
         3. Network policy

Rest:

  - ServiceAccount
  - RoleBinding
  - Role
  - Cert manager
  - Certificates
  - Pod / Node affinity
  - Helm
  - 

