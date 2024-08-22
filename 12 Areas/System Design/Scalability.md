# Vertical Scaling
- Adding more resources until the ceiling
- It is not the full solution
# Horizontal Scalling
- Add up nodes
- The problem is to distribute (load balance) the requests
## Load Balancing
![[Pasted image 20240624220920.png]]
- The load balancer is kind of a black box, that takes care of spreading out the resources to several machines
- Now what happens when something.com is accesses, which one of the server's ip address has to be returned
- Instead, the load balancer has an IP address and then it can take care of where to send the requests to
- The server can have private ip addresses