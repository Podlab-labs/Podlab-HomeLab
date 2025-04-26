![Alt text](./images/sabnzdb.jpg)

# SABnzdb

### Install

##### docker-compose.yml


```markdown
---
services:
  sabnzbd:
    image: lscr.io/linuxserver/sabnzbd:latest
    container_name: sabnzbd
    environment:
      - PUID=1000
      - PGID=1000
      - TZ=Australia/Sydney
    volumes:
      - /home/josh/docker/arr-stack/sabnzbd/config:/config
      - /mnt/downloads:/downloads #optional
      - /mnt/downloads/incomplete:/incomplete-downloads #optional
    networks:
      - media
    ports:
      - 8080:8080
    restart: unless-stopped

networks:
  media:
    external: true
```
