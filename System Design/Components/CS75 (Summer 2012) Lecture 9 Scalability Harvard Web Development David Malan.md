# How it works?
- We have to balance the load, based on how busy the backend servers are.
- But how do we get the busy characteristics of a server in first place
- Maybe the load balancer is just like a DNS, it could allocate the first request to first server and the next and next, [[Round Robin]]
![[Pasted image 20240624221747.png]]
## Problem with Round Robin Technique
- Axel says, the one server might get the hard & heavy requests.
	- Since we dont know the load state of a server, Round Robin just sends the heavy loaded server again, its nature.
	- And also caching can lead to disproportionation amount of load, due to ttls and the heavy user can stay on the same server
### Problem with Session data
- You'll have session cookie for each servers, which is a trouble, you'll have different carts. The user have to sent to same server for atleast for an hour\

- we could store session data in a separate file server, so we could share server states
- What to do if the session server fail, you'll be losing all the session states, single point of failure
- We'll be having different session
## RAID (Possibly outdated)
- Redundant Array of  Independed Disks
- commonly used in desktop computers (10yrs ago)
- it has variants
	- RAID0
		- Two identical Hard drives, but saves files in stripe manner
	- RAID1
		- Two identical hard drives, but you mirror every files.
		- if one fails, inserting other drive will duplicate the later
	- RAID10
		- both striping and redundancy and with 4 drives
	- RAID5
		- more drives, one of them used for redundancy
	- RAID6
		- Any two drives can drive.
### Problem with RAID
- But still we have downtime probabilty. 
	- Have more session servers
# Cookies
- Store the server ip in the cookie 
- user nth time visiting can be directed to the server with the ip
## What's wrong with this approach
- We don't need to expose server's ip and this can be solved by load balancer having a directory of random numbers with ip mapped
