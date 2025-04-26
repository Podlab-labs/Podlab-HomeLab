# iGotify

##### A small Gotify server notification assistent that decrypt the message and trigger a Push Notifications to iOS Devices via Apple's APNs with my service SecNtfy

Github Link below:

https://github.com/androidseb25/iGotify-Notification-Assistent

#### Update your data/volume paths to your own path details

e.g

```markdown
/home/ubuntu/docker/igotify/data
```
```markdown
/home/ubuntu/docker/igotify/api-data
```

#### If using Traefik. Update your labels to use your domain details.

gotify port 80
igotify port 8080

e.g Labels

```markdown
labels:
  - "traefik.enable=true"
  - "traefik.http.routers.gotify.entrypoints=http"
  - "traefik.http.routers.gotify.rule=Host(`gotify.podlab.tech`)"
  - "traefik.http.middlewares.gotify-https-redirect.redirectscheme.scheme=https"
  - "traefik.http.routers.gotify.middlewares=gotify-https-redirect"
  - "traefik.http.routers.gotify-secure.entrypoints=https"
  - "traefik.http.routers.gotify-secure.rule=Host(`gotify.podlab.tech`)"
  - "traefik.http.routers.gotify-secure.tls=true"
  - "traefik.http.routers.gotify-secure.service=gotify"
  - "traefik.http.services.gotify.loadbalancer.server.port=80"
  - "traefik.docker.network=proxy"
```