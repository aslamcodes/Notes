Robots.txt
- Every domain has this file that is like a "Code of Conduct" for those bots
- `Robot.txt` can't actually enforce its rules, its just saying

> [!INFO] Fact 
> Every domain will have a `robots.txt` file hosted in its domain
- A Good bot will abide by it, a bad one is likely to break it
- A Good bot will look at it first before visiting any other page on the site
## Structure
```text
- User Agent: User_agent_name 
	// rules
- User Agent: User_agent_name_2
    // rules
```
## Protocols
> In networking, a [protocol](https://www.cloudflare.com/learning/network-layer/what-is-a-protocol/) is a format for providing instructions or commands.
- Robot.txt follow various protocols
	- Robots Exclusion Protocol - Tells what web pages to avoid 
	- Sitemap protocols (inclusion) - Tells what web pages they can crawl 
### Robots Exclusion Protocol's commands
- `Disallow`
- `Allow`
- `Crawl-delay`
- ....
### Sitemap Protocols
> The Sitemaps protocol helps bots know what to include in their crawling of a website.
![Sitemap example](https://cf-assets.www.cloudflare.com/slt3lc6tev37/55ZlRHspOLayKpPlr6kmaO/e4f0964c2831d18774037cf1f6557eb0/sitemap-example.png)
https://www.google.com/sitemap.xml

Sitemaps can be included in the robots.txt file in this format
```
sitemaps:https://www.google.com/sitemap.xml
```

> [!INFO] A Good Robots.txt file
> For bot management, a good robots.txt file will make the site better optimised for SEOs, and can help bot activities under control, but can't enforce over them.

> For malicious bots robot.txt can't do much.


# References
https://www.cloudflare.com/en-in/learning/bots/what-is-robots-txt/