[Kubefed](https://github.com/kubernetes-sigs/kubefed) is a Kubernetes [Operator](https://coreos.com/operators) that provides tools for managing applications and services through multiple Kubernetes clusters. 

Kubefed allows users to:

* Distribute workloads across registered clusters

* Program DNS with information about those workloads

* Dynamically adjust replicas in the different clusters a workload is deployed in

* Provide disaster recovery for those workloads

As Kubefed matures, we expect to add features related to storage management, workload placement, etc.

Kubefed takes advantage of new mechanisms in order to extend the Kubernetes API and provide an easy interface for users to interconnect their Kubernetes clusters without having to deal with network latencies, etcd requirements, etc.

The Kubefed control plane is composed of an Operator running on one of the federated clusters. This Operator is in charge of some [CRDs](https://kubernetes.io/docs/tasks/access-kubernetes-api/custom-resources/custom-resource-definitions/) which will be discussed later on in this course.

|Concept|Definition|
|-------|----------|
|Host Cluster|A cluster which is used to expose the Kubefed API and run the Kubefed Control Plane|
|Member Cluster|A cluster which is registered with the Kubefed API and that Kubefed controllers have authentication credentials for. The Host Cluster can also be a Member Cluster.|
