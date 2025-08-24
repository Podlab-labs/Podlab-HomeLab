#### Create the secret in terminal

```markdown
openssl rand -base64 32 | tr -dc 'a-zA-Z0-9' | head -c 32
```
#### Generate user and password for a user

```markdown
"echo $(htpasswd -nB user) | sed -e s/\\$/\\$\\$/g"
```
