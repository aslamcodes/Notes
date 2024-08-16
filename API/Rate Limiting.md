![[rate-limiting.png]]
> Puts on a cap on how frequent one may query the server

#review
- Protects from API overuse
# Bot Attacks that can be mitigated
[[DDoS]] 
[[DoS]]
[[Web Scraping]]
[[Brute Force Attacks]]
# How?
- Tracking [[IP address]]es, and their request and their time delta from the previous one and the current.
- If exceeds, pulls over the user like a cop
# User Logins
- Attackers might try to brute-force into user credentials if rate limiting is not implemented in login level
- if its only IP address level - attackers can use multiple IPs to crack the password
- If its only username level - attackers can use brute-force with common passwords
# API
- API owners have to pay for the compute time that each request takes.
- For this reason, limitations are imposed upon API users.
- Such as how many for a hour, day for each user
- It helps preventing [[DDoS]] and [[DoS]] 
# Bot Management vs Rate Limiting
- Rate limiting cannot distinguish between good bots and malicious bots. 
- But in [[Bot Management]] tools, holistically malicious bot activity can be detected with the help of ML algorithms.
# Rate Limiting Algorithms
- 
# Rate Limiting endpoints in ASP.NET
1. Define a Rate Limiting Policy
2. Use the Policy with Attributes
```csharp
var builder = WebApplication.CreateBuilder(args);

builder.Services.AddRateLimiter(_ => _
    .AddFixedWindowLimiter(policyName: "fixed", options =>
    {
        options.PermitLimit = 4;
        options.Window = TimeSpan.FromSeconds(12);
        options.QueueProcessingOrder = QueueProcessingOrder.OldestFirst;
        options.QueueLimit = 2;
    }));
```
