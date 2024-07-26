---
sr-due: 2024-07-13
sr-interval: 3
sr-ease: 250
---

#review
# Type of EC2 Instances
- AWS has different types of EC2 instances
- Each instance type is grouped under instance family
## Instance families
- General purpose - Good balance of compute, memory and storage like backend servers, gaming servers and dbs
- Compute Optimized - Compute intensive like gaming servers, HPC, Scientific modeling
- Memory Optimized - Memory intensive tasks
- Accelerated Computing - Floating point number calculations, Graphics processing or data pattern matching
- Storage Optimized - Good for storage
### General Purpose
Suppose that you have an application in which the resource needs for compute, memory, and networking are roughly equivalent. You might consider running it on a general purpose instance because the application does not require optimization in any single resource area.
### Accelerated Computing Instances
- use hardware accelerators & coprocessors > software running on cpu
- #todo what is [[Hardware acceleration]]
### Memory  
>  designed to deliver fast performance for workloads that process large datasets **in memory.**
-  memory is a temporary storage area.
-  Before a computer program or application is able to run, it is loaded from storage into memory. This preloading process gives the CPU direct access to the computer program.
### Storage Optimized
- Designed to deliver ***low latency***, ***random*** IOPS
- Suitable for storage optimized instances include
	- distributed file systems, 
	- data warehousing applications, and 
	- high-frequency online transaction processing (OLTP) systems.
- #todo Why DFS and Data warehousing and OLTP need higher IOPS