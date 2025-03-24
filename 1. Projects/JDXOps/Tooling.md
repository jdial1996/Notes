**Kubernetes** to support container based microservice architecture (instead of monolithic application)
- Scalability
	- Cluster Resizes by itself
	- Pods scale depending on traffic
	- Self healing 
- Microservices Architecture  
	- Scale each application microservice independently
	- If one part of the application breaks it doens't break down the whole application (no single point of failure)
	- **Faster innovation**: microservices + containers mean quicker feature rollouts.
- No vendor lock in 
	- Cloud agnostic
- Cost efficiency
	- K8s efficiently schedules pods onto nodes (cluster packing)
	- Resizes cluster when nodes are not needed 

**IaC (Infra as code)**
- Terraform modules made available to engineering teams to foster collaboration between Dev and Ops.  Engineering Teams can use modules to provision infrastructure or contribute to modules by submitting a PR to the terraform module github repo and having ops review it. 
- IaC is repeatable and automated. This  reduces manual effort and risk of human error, enabling faster and more reliable deployments.
- IaC is scalable: Teams can spin up complex environments in minutes—greatly improving development velocity and productivity.
- Cost efficient: Infrastructure is no longer “snowflakes.” Easily tear down or modify environments to optimize cost.
	**Auditability & Compliance**
	
	- **Everything is code**: All infrastructure changes are version-controlled, reviewed, and traceable.
	    
	- Makes compliance audits easier and improves visibility into who changed what, when, and why.