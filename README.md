# FastAccessControl Server

FastAccessControl Server is a high-performance, secure, pure-Python socket server & client for distributed rate limiting and IP access control to your API services — all in under 0.0001s (plus network latency).

✨ Highlights 

- High performance with low memory usage: handles thousands of concurrent connections efficiently.

- Built-in IP Firewall and Rate Limiting: instantly decides whether an IP is allowed to access the service. Fully configurable.

- It has lists of permanent allowed access, permanent blocked access and unlimited access (for the ratelimiter). You can change these lists and rate limit settings at runtime.

- It has its own smart cache which further speeds up queries regardless of the size of the IP/CIDR exception list.

- Support for multiple configurations: unique block/allow lists and specific rate limit rules for different client applications.

- Serve multiple protocols simultaneously: supports TCP, UDP, and TLS (I know it's crazy, but...), each with configurable bind addresses and ports, and works with IPv4 and IPv6 simultaneously, both on the client side or server side.

- Cross-platform: runs on Linux, macOS, Windows, Docker, and Kubernetes.

- Security-hardened: It is a service to stay on internal networks, but is protected against buffer overflow attacks, with support for request timeouts as low as 0.01 seconds.

- Privilege dropping support: drop privileges after starting the server (Linux and macOS).

- Multiple workers and CPU affinity control on Linux servers: one core for each worker.

| Example 1: | Example 2: | 
| ------------------------------------- | ------------- | 
|<img src="https://raw.githubusercontent.com/rabuchaim/fastaccesscontrol/refs/heads/main/screenshot01.png" width="600" />|<img src="https://raw.githubusercontent.com/rabuchaim/fastaccesscontrol/refs/heads/main/screenshot02.png" width="600" />| 

### Work-in-progress:

1. Geo-based IP access control: block or allow access by country using a custom version of [GeoIP2Fast](https://github.com/rabuchaim/geoip2fast). Supports [GeoIP2Fast dat files](https://github.com/rabuchaim/geoip2fast/releases/tag/LATEST) (with automatic updates and 99.67% of coverage using only 25MB RAM) or any MMDB file from any geoip provider. 

2. Replica servers working in standby mode in case the primary server becomes unavailable.

3. Replica servers working in read-write mode with fast and intelligent replication between peers.

4. Reverse DNS-based access control with an integrated DNS client.

