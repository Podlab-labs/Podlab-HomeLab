![Alt text](./images/jellyfin.jpg)

### Note that at present time, Jellyfin is hosted in  LXC container deployed on Proxmox.

# This should be close to what is needed for a docker install.

# Jellyfin Install

```markdown
---
services:
  jellyfin:
    image: lscr.io/linuxserver/jellyfin:latest
    container_name: jellyfin
    environment:
      - PUID=1000
      - PGID=1000
      - TZ=Etc/UTC
      - JELLYFIN_PublishedServerUrl=192.168.1.23 #optional
    volumes:
      - /path/to/docker/jellyfin/config:/config
      - /mnt/media/tv:/data/tvshows
      - /mnt/media/movies:/data/movies
      - /mnt/media/music:/data/music-videos
    ports:
      - 8096:8096
      #- 8920:8920 #optional
      #- 7359:7359/udp #optional
      #- 1900:1900/udp #optional
    networks:
       -media  
    restart: unless-stopped

networks:
  media:
    external: true    
```

#### Hardware Accelaration / Transcoding

```markdown
--device=/dev/video10:/dev/video10
--device=/dev/video11:/dev/video11
--device=/dev/video12:/dev/video12
```

