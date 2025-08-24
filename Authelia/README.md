# Authelia Install Guide

This container is placed on the `proxy` docker network

`Using Nginx Proxy Manager`

If using the same docker network for the Authelia containers as Nginx Proxy Manager you can use the container names instead of the ip addresses.

#### Create the following

I have all my docker containers organised in my home folder:

/home/josh/docker

```markdown
mkdir authelia
```
```markdown
cd authelia
```

```markdown
touch docker-compose.yml
```

```markdown
mkdir config 
```
docker-compose.yml is a multi container with `redis`

Small database as only a handful of users. Using `sqlite3`

Argon2 command for password:

```markdown
docker run -it authelia/authelia:latest authelia crypto hash generate argon2
```
