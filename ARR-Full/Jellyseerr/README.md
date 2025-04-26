![Alt text](./images/jellyseerr.png)

# Jellyseer

### Install

##### docker-compose.yml

```markdown
---
services:
    jellyseerr:
       image: fallenbagel/jellyseerr:latest
       container_name: jellyseerr
       environment:
            - LOG_LEVEL=debug
            - TZ=Australia/Sydney
       ports:
            - 5055:5055
       volumes:
            -  /path/to/docker/arr-stack/jellyseerr/config:/app/config
       networks:
         - media
       restart: unless-stopped

networks:
  media:
    external: true
```
