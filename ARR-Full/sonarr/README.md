![Alt text](./images/sonarr-banner.png)

# Sonarr

### Install

##### docker-compose.yml

```markdown
---
services:
  sonarr:
    image: lscr.io/linuxserver/sonarr:latest
    container_name: sonarr
    environment:
      - PUID=1000
      - PGID=1000
      - TZ=Australia/Sydney
    volumes:
      - /path/to/docker/arr-stack/sonarr/data:/config
      - /mnt/media/tv:/tv #optional
      - /mnt/downloads:/downloads #optional
    ports:
      - 8989:8989
    networks:
      - media
    restart: unless-stopped

networks:
  media:
    external: true
```
