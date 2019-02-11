# Hazelcast Helm Operator

This hazelcast operator is built using [operator-sdk](https://github.com/operator-framework/operator-sdk/blob/master/doc/helm/user-guide.md).

This operator will deploy and manage hazelcast clusters based on the helm chart.
The chart includes prometheus jmx exporter to expose prometheus jmx metrics for the hazelcast clusters


## Prerequisites

- [git][git_tool]
- [docker][docker_tool] version 17.03+.
- [kubectl][kubectl_tool] version v1.11.3+.
- [dep][dep_tool] version v0.5.0+. (Optional if you aren't installing from source)
- [go][go_tool] version v1.10+. (Optional if you aren't installing from source)
- Access to a kubernetes v.1.11.3+ cluster.

## Deploy

Deploy the crd
```
kubectl create -f deploy/kanzifucius_v1alpha1_hazelcast_crd.yaml
```

Deploy the operator 
```
kubectl create -f deploy/service_account.yaml
kubectl create -f deploy/role.yaml
kubectl create -f deploy/role_binding.yaml
kubectl create -f deploy/operator.yaml
```

## Build 
Please see operator sdk documentation [helm user guide](https://github.com/operator-framework/operator-sdk/blob/master/doc/helm/user-guide.md)


eg
```
operator-sdk build kanzifucius/hazelcast-helm-operator:v0.1
docker push kanzifucius/hazelcast-helm-operator:v0.1
```
