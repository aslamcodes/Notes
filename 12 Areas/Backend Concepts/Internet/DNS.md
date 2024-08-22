# Terms
**DNS Recursor resolver** - Receive DNS requests from client machines, and job is on the recursor's hands
**Root Nameserver** - Just like an Index to TLD servers, such as .com, .in
**Authoritative nameserver** - Holds the translation for the domain name

![server](https://cf-assets.www.cloudflare.com/slt3lc6tev37/3NOmAzkfPG8FTA8zLc7Li8/8efda230b212c0de2d3bbcb408507b1e/dns_record_request_sequence_recursive_resolver.png)![](https://cf-assets.www.cloudflare.com/slt3lc6tev37/1NzaAqpEFGjqTZPAS02oNv/bf7b3f305d9c35bde5c5b93a519ba6d5/what_is_a_dns_server_dns_lookup.png)
# DNS Queries
1. Recursive Queries - The DNS Server(resolver) returns with the requested result or with an Error Message.
2. Iterative Queries - The DNS server returns the requested result or points to other lower level servers (Road Trip)
3. Non-recursive queries - The final query with the authoritative server or the query from the cache
# DNS Caching
DNS data can be cached in variety of locations, with a TTL (Time to live)
1. Browser - check the browser cache at `chrome://net-internals/#dns.`
2. OS level DNS resolver
	1. A OS Process, called **Stub Resolver**, has its own cache.
	2. If cache dont have what the application asked for it sends DNS query to a **DNS resolver** inside the **ISP** with a recursive flag
	3. The **DNS Resolver** inside the **ISP** has its own ***cache***
	4. The DNS resolver does different functionality based on the records it has
		1. if it not have **A Record**s, but has **NS records**, then it'll skip querying **TLD server** and query the **name servers**
		2. if it doesn't have **NS records**, it'll ask for **TLD server** without asking the **Root**
		3. if it doesn't have both, it'll ask for the root server (highly unlikely)

```embed
title: "What is DNS? | How DNS works"
image: "https://cf-assets.www.cloudflare.com/slt3lc6tev37/3FQ0nr0TWKiiXvr1sipYj5/df80437167ef2215bb09fc00ba0429fc/dns_og.jpeg"
description: "DNS, or the domain name system, is the phonebook of the Internet, connecting web browsers with websites. Learn more about how DNS works and what DNS servers do."
url: "https://www.cloudflare.com/en-gb/learning/dns/what-is-dns/"
```
```embed
title: "How DNS works. What is DNS? Learn how step by step."
image: "https://t2.gstatic.com/faviconV2?client=SOCIAL&type=FAVICON&fallback_opts=TYPE,SIZE,URL&url=https://howdns.works/&size=128"
description: "Learn what is the domain name system (DNS) that brings computers and IP addresses together when you type a website address in your browser with our webcomic."
url: "https://howdns.works"
```
## Records
The entries in a DNS
### A Record 
- A stands for address records.
- A stores IPv4 addresses, and AAAA stores IPv6 address
![[Screenshot 2024-08-09 at 5.31.26 PM.png]]
### NS Record
- NS stands for Name space record
- Indicates DNS Server authoritative for that domain
- The Name server holds all the A Records and MX Records for that domain.
- There is more than on nameserver, so no single point of failure.
![[Screenshot 2024-08-09 at 5.32.32 PM.png]]