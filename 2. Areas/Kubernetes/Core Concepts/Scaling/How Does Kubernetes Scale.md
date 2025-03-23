- When the traffic destined for a Kubernetes application increases, we need to deploy more instances of the application so that it can handle the increased traffic.   So we need to go from 1 EC2 instance serving traffic to multiple.


**Pod Scaling**
- In the dataplane you have multiple woker nodes running (eg. Amazon EC2).  Inside each worker node you have 1 or more pods running.  Each pod has 1 or more containers running.
- Pods serve traffic using a Kubernetes service and they have some level of CPU and Memory allocated
- As demand on a pod increases, we can deploy more instances of it using the **Horizontal Pod Autoscaler (HPA)**. 
- The HPA can be triggered of CPU, Memory and other metrics. 
- The HPA looks at average resource utilisation (CPU and Memory)  across an entire deployment.  So you would set the scaling rule to something like **if average CPU utilisation is at 50% then increase the number of pods in the deployment by 1.**
- Once the HPA decides a new pod is created but it goes into a "Pending Status" as it waits to be scheduled onto a dataplane node by the **KubeScheduler** 
- If there is a node with available capacity that meets scheduling constraints in the Kubernetes cluster, the pod will be scheduled onto that node.  If there is not then the pod will be given a **'pending,unschedulable'** status.  
- This status will be picked up by either **Karpenter** or the **Cluster Autoscaler**, whose role will be to scale the node up to accommodate for the additional pod. 

**Node Scaling**
- The NodeScalers (Cluster Autoscaler or Karpenter) look out for pods that have a **pending,unschedulable** status.
- Once such a pod is identified, the node scalers will add an additional node to the cluster to accommodate the additional pod. 

[[Cluster Autoscaler]]
[[Karpenter]]
[[Metrics Server]] (required by the HPA)