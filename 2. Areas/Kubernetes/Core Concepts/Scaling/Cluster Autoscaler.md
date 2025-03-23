- The cluster autoscaler scales a component that resizes a Kubernetes cluster by adding or removing worker nodes.  This ensures that there is always capacity for additional pods and that worker nodes are not being underutilised 
- Nodegroups are tied to autoscaling groups in AWS, which require configuration such as the Instance ID to be specified in the **Launch Template**.   
	- For this reason one nodegroup can only have one type of instance (ami id, instance type etc) 

- When there are unschedulable pods and no available capacity in the cluster, the Cluster Autoscaler will scale an autoscaling group associated with an existing nodegroup. 

[[Autoscaling Groups]]