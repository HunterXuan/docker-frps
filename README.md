# frps-docker
frps running in docker
## How to use
Assume that 22222 is the port you choose for ssh proxy. Here's a docker-compose.yml example.
```yaml
version: "3.4"
services:
  frps:
    image: hunterxuan/frps-docker
    volumes:
      - /path/to/your/frps.ini:/usr/local/frps/frps.ini
    ports:
      - target: 7000
        published: 7000
        mode: host
      - target: 7001
        published: 7001
        protocol: udp
        mode: host
      - target: 22222
        published: 22222
        mode: host
```
