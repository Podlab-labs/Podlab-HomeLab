# Crowdsec for Traefik Info

## Exec command for API key  
### API key to place in Crwodsec docker-compose.yml

```markdown
sudo docker exec crowdsec cscli bouncers add bouncer-traefik
```
##### Redeploy  Crowdsec

```markdown
docker compose up -d
```
### Crowdsec Commands

https://docs.ibracorp.io/crowdsec/crowdsec/useful-commands