**IOPs**
- IOPS (Input/Output operations) is the number of read/write operations that can occur per second on an EBS volume. 
- GP3 EBS Volumes come with a default of 3000 IOPs free and they can scale up to 16000 IOPs per volumes

**Throughput**
- Throughput is the maximum megabytes per second that an EBS volume can process.
- GP3 volumes by default can process 125mb/s and this can be scaled up to 1000mb/s at an additional cost 

**IOPs and Throughput Relationship**
- IOPs and Throughput are positively correlated.  An increase in one leads to an increase in the other. 

**Throughput Formula**
$$
\text{Throughput (MB/s)} = \frac{\text{IOPS} \times \text{Block Size (KB)}}{1024}
$$

