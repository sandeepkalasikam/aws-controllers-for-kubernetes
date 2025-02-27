# EKS Service Controller Examples

In this folder you can find general examples for creating EKS Resources from
your Kubernetes Cluster with ACK (AWS Controllers for Kubernetes).

Basic EKS creation:

```yaml
apiVersion: eks.services.k8s.aws/v1alpha1
kind: Cluster
metadata:
  name: $CLUSTER_NAME #Change the Cluster Name
spec:
  name: $CLUSTER_NAME #Change the Cluster Name
  roleARN: $CLUSTER_ROLE #Change the Cluster Role
  resourcesVPCConfig:
    endpointPrivateAccess: true
    endpointPublicAccess: false
    subnetIDs:
      - "$PUBLIC_SUBNET_1" #Change the first Subnet ID
      - "$PUBLIC_SUBNET_2" #Change the second Subnet ID
  version: $KUBERNETES_VERSION #Change the Kubernetes Version
```

## Create the EKS Repository

```bash
kubectl apply -f <file_name> #Change the file name accordingly
```

## Delete the EKS Repository

```bash
kubectl delete cluster <cluster_name> #Change the cluster name accordingly
```
