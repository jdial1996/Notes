**Step 1 - Create IAM Roles**
- Before you create the EKS Cluster controlplane, create an EKS Cluster IAM role with the AmazonEksClusterPolicy (arn:aws:iam::aws:policy/AmazonEKSClusterPolicy) attached so that the EKS cluster can manage nodes.
- For worker nodes before they are launched and added into a cluster, you must create an IAM role for htose nodes to use when they are launched. 
	- Create the role and attach EKSWorkerNodePolicy, EC2ContainerRegistryPullOnlyPolicy, AmazonEKS_CNI_Policy