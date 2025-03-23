- An Autoscaling Group (ASG) is a collection of EC2 instances that are treated as a logical grouping for the purposes of automatic scaling. 
- The ASG will initially launch enough instances to meet the **desired capacity** requirements.  It will maintain this number of instances by performing periodic health checks on the instances in a group. 
	- If an instances becomes unhealthy the ASG terminates the unhealthy instance and launches another instance to replace it (to maintain the desired capacity).
- The ASG will use a launch template as a configuration template for EC2s.  The launch template specifies information such as the AMI Id, instance type, key pair, security groups and block device mappings for EC2s


**Launching a new instance in an ASG**
- A new instance is launched. If the launch succeeds, it gets added to the Autoscaling Group 
- The Autoscaling Group performs health checks on the instance by using built in Amazon EC2 status checks and after a grace period any optional health checks that have been enabled for the group 
- The health checks continue periodically and if any fail the instance is replaced. 

![[Pasted image 20250323103721.png]]