***Cluster Security Group***

- When an EKS cluster is created, a default security group is created for the whole cluster that enables all communication between the control plane and worker nodes.
- When managed nodegroups are provisioned, by default they inherit this security group (cluster security group)