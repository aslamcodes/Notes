---
sr-due: 2024-08-11
sr-interval: 3
sr-ease: 250
---

#review
# Clones (Nodes)
- The adjective scalable web service are hidden behind [[Load Balancer]]
- It'll distribute the load into groups/clusters of app servers and all app servers are identical in processing requests and user data should be present (sessions, cookies...)
> first golden rule for scalability: every server contains exactly the same codebase and does not store any user-related data, like sessions or profile pictures, on local disc or memory.
- Sessions can be stored in centralized stores such as external cache ([[Redis]]) or external database
## Deployment 
- All servers need to have the same code changes
- This can be done with tools like [[Ansible]], [[Jenkins]], ([[Github Action]] ig?)
# Database
- Even though the system can be horizontally scalable, the system will eventually get slow because of the MySQL database, author suggest that there are two options
## Path 1
- Author sarcastically mentions path 2 is better off
- Instead of doing [[Master-Slave Replication]], [[Sharding]], [[denormalization]] and [[SQL tuning]] and other expensive things to keep DB running, we can go for Path 2
## Path 2
### w SQL
- Denormalise from the beginning
- No Joins in db query
- Use SQL db as a NoSql Db
### w/o sql
- Swtich to NoSQL
- Easier to scale
- Joins will be done on app code

> [!DANGER] SQL vs NoSQL
> Is SQL that bad, we cannot have any SQL in a scalable productions as the author mentions

Even after doing the path 2, your app will be slowing down, Do Caching

# Caching
#todo
# Asynchronism
> [!NOTE] By Asynchron-ism, the author means process that are asynchronous by nature such as SSR and Job Queuing
- The author compares asynchronism to a bakery
- A Synchronous bakery would make the customer wait for every orders
- An Asychronous bakery would have two ways of handling this problem
	- Common Orders - Bake the breads before each night and serve morning with no delays, Happy customer
	- Special Orders - Special Orders are queued
- The Common Orders are analogous to **SSG**, where dynamic HTML are converted to static html and put on to the CDN and fast response time *Happy Users*
- The Special Order are analogous to **Job Queues**, the intensive workload are sent to the queue and the UI is free and the user can pick it up once the job is done.
