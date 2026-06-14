
so, for your internet to work, you can generally check the following things in the following order (on any device):

-1: is your network adapter detected?

-2: do you have a default gateway? (this is your router)

-3a: if your router provides DHCP: is your DHCP daemon/service running and did you receive an IP?

-3b: if your router does not provide DHCP: do you have an IP statically configured?

-4: can you *ping* the default gateway successfully?

-5: can you *ping* [1.1.1.1](http://1.1.1.1) or [8.8.8.8](http://8.8.8.8) successfully? (these are the ip addresses of cloudflare dns and google dns)

-6: can you resolve a hostname using nslookup?

-7: can you resolve a hostname using nslookup with the dns 1.1.1.1?

  

if all these pass, you have internet and whatever isn't working is being specifically blocked (for example by a network block, an ACL or a firewall rule)

  

here's what these tests mean if they fail but all previous tests succeed:

-1: your network adapter has no drivers or is dead, either install the drivers or swap to a different network adapter

-2: your device doesnt know the router exists, either because the router's DHCP cant reach it, or the router isn't providing DHCP, or if no DHCP is being used the device just hasn't been configured with static details.

-3: you can't reach the internet because your device does not have an address.

-4: your device is configured, but cannot reach the router or the router is offline

-5: your device is configured and can reach the router, but the router cannot reach the internet.

-6: if the ip address used looks like [127.0.0.1](http://127.0.0.1), you are using the resolver stub and it is not working correctly, if it starts with 10.xx, 192.168 or 172.xx, you're using a local DNS server and that server is not working correctly (most likely, this matches your default gateway)

-7: if the previous one failed, this one won't always fail. in that case, it means your local DNS server is broken but public DNS works fine. if this one fails when 6 worked, it means you have no internet. if both fail, it's unlikely to be your DNS server.

  
it boils down to 3 components: your IP, your DNS server and your DHCP server.

  
lets start with IP: your IP is an address that allows computers to know where to route information, normally, your desktop/laptop will have an *internal* IP address. your router has both a public one and a private one, and hosts a network using the private IP on which other devices can have their own addresses. when a request comes into the router, the router will look at it and forward it to the correct IP.

imagine it as multiple housemates living under one roof with one address, they each have a little mailbox next to their bedroom door and one of the housemates takes the letters from the main mailbox every day and distributes them to the right mailboxes based on how those letters are addressed.

  
in order for your device to have an IP, it needs to be configured. the router and device also need to *agree* on the IP. this can be done in two ways:

manual configuration means you go into your settings and you manually type out the netmask, default gateway, DNS address and the address you want your device to have. this is done without any agreement from the router, the router just has to deal with the device having this IP address. if you set it up wrong, you wont have internet at all, and if you set up two devices to have the same address, both will no longer have internet until the issue is resolved or one device goes offline.

  
dhcp is a protocol that allows you to hand out IPs automatically on a lease, computers can subsequently renew the lease if they're still online, and once the lease runs out and isn't renewed, it gets put back into the pool of available addresses.

this is done by a DHCP server, which generally runs on your router. it hands out the default gateway, addresses, the netmask and the default DNS server. you can configure the settings for the DHCP server including what it hands out in your router.

  
lastly, the DNS server. this is kinda the magic sauce of networking.

your DNS server is responsible for taking the hostnames you put into *any* of your applications (like your browser) and turning them back into an IP. this is because those hostnames cant be used directly to navigate the internet.

so instead, when you key in "reddit.com" on firefox, your computer actually sends a request to your DNS server first saying "hey, what is the IP for reddit.com".

and then, assuming everything works, gets the response [151.101.129.140](http://151.101.129.140) (this is one of reddit's IP addresses).

  
linux has the option of using a stub resolver, or resolver cache, windows also has this by default. what that will do is: once your computer has asked about the IP for [reddit.com](http://reddit.com), it'll store that result in the resolver cache.

effectively, this resolver cache is treated as its own DNS server, running on your machine, that just forwards the request if it doesn't know.
