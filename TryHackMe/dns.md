# DNS (Domain Name System)

DNS (Domain Name System) provides a simple way for us to communicate with devices on the internet without remembering complex numbers.

## Domain Hierarchy

![alt text](/TryHackMe/images/image.png)

## Types of DNS

### A record
Resolve  IPV4 addresses, for example 104.26.10.229.

### AAAA record
Resolve IPv6 addresses, for example 2606:4700:20::681a:be5.

### CNAME records
These records resolve to another domain name, for example, TryHackMe's online shop has the subdomain name store.tryhackme.com which returns a CNAME record shops.shopify.com. Another DNS request would then be made to shops.shopify.com to work out the IP address.

### MX record
These records resolve to the address of the servers that handle the email for the domain you are querying, for example an MX record response for tryhackme.com would look something like alt1.aspmx.l.google.com. These records also come with a priority flag. This tells the client in which order to try the servers, this is perfect for if the main server goes down and email needs to be sent to a backup server.




