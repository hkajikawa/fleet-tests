# Multi-Cluster Kustomize Example

This example will deploy the [Kubernetes sample guestbook](https://github.com/kubernetes/examples/tree/master/guestbook/) application
using kustomize. The app will be deployed into the `fleet-kustomize-example` namespace.

The application will be customized as follows per environment:

```yaml
kind: GitRepo
apiVersion: fleet.cattle.io/v1alpha1
metadata:
  name: fleet-test
  namespace: fleet-default
spec:
  branch: main
  repo: https://github.com/hkajikawa/fleet-tests
  paths:
  - multi-cluster/kustomize
  targets:
    - clusterSelector: {}
```
