# Concepts
- cluster: multiple nodes
  - master-slave architecture
  - 1 master node, several worker nodes 
- Container: applications, software, libraries, etc, providing a stand-alone and OS isolated environment for application to run.
- Pod: a collection of containers, with shared storage and network, it is the schedule unit of k8s. 
  - each pod has its own IP address
  - containers within a pod share the IP address, port space and can find each other via localhost
- Replicaset: runs a number of pods, based on the provided template.
- Service: Manage the network of pods
  - Services operate on Layer 4(TCP/UDP over IP) in the OSI model.
- Deployment: manage multiple replicasets for 
- ConfigMap/Secrets: 12-factor app manifesto. Map configuration files into pod as environment variables.
- DaemonSet:
- Ingress:

# Readings
- https://www.cncf.io/blog/2019/05/10/kubernetes-core-concepts/

