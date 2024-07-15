# Milestone 6
# CDN(Content Delivery Network)
## What is CDN?
- CDN stands for Content Delivery Network
- It is a geagraohically distributed group of servers that caches content clode to end users.It allows for the quick transfer of assets needed for loading internet content,including html pages, js files , stylesheets, images and videos.
- A properly configured CDN may also help protect websites against some common malicious attacks, such as Distributed Denial of Service (DDOS) attacks.
## Benefits of using a CDN:
The primary benefits includes:
1. Improves website load times:
  By distributing content closer to website visitors by using a nearby CDN server , visitors experience faster page loading times. As visitors are more inclined to click away from a slow-loading site, a CDN can reduce bounce rates and increase the amount of time that people spend on the site. In other words, a faster a website means more visitors will stay and stick around longer.

2. Reduces bandwidth costs:
   Bandwidth consumption costs for website hosting is a primary expense for websites. Through caching and other optimizations, CDNs are able to reduce the amount of data an origin server must provide, thus reducing hosting costs for website owners.
   
3. Increased availability and redundancy:
  Large amounts of traffic or hardware failures can interrupt normal website function. Thanks to their distributed nature, a CDN can handle more traffic and withstand hardware failure better than many origin servers.
4. Website security improved :
  A CDN may improve security by providing DDoS mitigation, improvements to security certificates, and other optimizations.

## Metrics of CDN:
There are 3 metrics for CDN:
- RTT:
  `Round-trip time` is the duration in millisecond(ms) it takes for a network request to go from a starting point to a destination and back again to the starting point.
  Factors that affects RTT:
    >Transmission medium nature
    >LAN traffic
    >Server response time
    >Node count
    >Physical Distance

- TTL:
  `Time to live`  refers to the amount of time or “hops” that a packet is set to exist inside a network before being discarded by a router.
  Working:
   >packets are designed with an expiration called a time-to-live or hop limit.
   >Every time a router receives a packet, it subtracts one from the TTL count and then passes it onto the next location in the network
   >At any point,if the TTL is zero the router discards.

- Cache hit ratio: It is the measurement of how many content requests a cache is able to fill successfully, compared to how many requests it receives.

- Cache hit ratio =No. of cache hits/(No. of cache hits + No. of cache misses)

  ## Static and Dynamic Cache:
  - `Static Cache` :Static content is any file that is stored in a server and is the same every time it is delivered to users.
  - `Dynamic Cache` :Dynamic content is content that changes based on factors specific to the user such as time of visit, location, and device.

## Data Center
Housing where networked computers work together to process, store, and share data.

## Origin Server:
It is the Actual main physical server of a website or other service providers.

## Edge Server:
A CDN edge server is a computer that exists at the logical extreme or “edge” of a network.

## IXP:
Stands for Internet exchange point.physical location through which Internet infrastructure companies connect with each other.

## GSLB:
Global server load balancing or GSLB used in distributing Internet traffic amongst a large number of connected servers dispersed around the world.

## SSL/TLS Encryption:
Its a protocol for encrypting data.It is designed to provide 3 components:
- Authentication
- Encryption
- Integrity
  ## SSL Certificate:
  Certificates are files containing information about the owner of a site and the public half of an asymmetric key pair.
  ## TCP/IP Handshake:
  1. Client send SYN PAcket to server.
  2. Server Responds SYN/ACK packet, for acknolegdement.
  3. Client send ACK back to server.
   
