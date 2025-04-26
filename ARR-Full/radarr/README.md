![Alt text](./images/radarr.png)

# Radarr

### Install

##### docker-compose.yml


```
---
services:
  radarr:
    image: lscr.io/linuxserver/radarr:latest
    container_name: radarr
    hostname: radarr
    environment:
      - PUID=1000
      - PGID=1000
      - TZ=Australia/Sydney
    volumes:
      - /path/to/docker/radarr/data:/config
      - /mnt/media/movies:/movies #optional
      - /mnt/downloads:/downloads #optional
    networks:
      - media  
    ports:
      - 7878:7878
    restart: unless-stopped

networks:
  media:
    external: true   