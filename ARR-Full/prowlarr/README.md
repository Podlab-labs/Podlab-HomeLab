![Alt text](./images/prowlarr.png)

# PROWLARR

### Install

##### docker-compose.yml

```
---
services:
  prowlarr:
    image: lscr.io/linuxserver/prowlarr:latest
    container_name: prowlarr
    environment:
      - PUID=1000
      - PGID=1000
      - TZ=Australia/Sydney
    volumes:
      - /path/to/docker/prowlarr/data:/config
    networks:
      - media  
    ports:
      - 9696:9696
    restart: unless-stopped
    
networks:
  media:
    external: true