# Practice 2
---
## Requirements:
```
Deploy WordPress with Docker Compose

```
---
## Guide
After complete practice 1, we have already install VituralBox, Ubuntu and Docker
**1. Install Docker compose**
- Run this command to download the current stable release of Docker Compose
```
$ sudo curl -L "https://github.com/docker/compose/releases/download/1.29.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

```
- Apply executable permissions to the binary
```
$ sudo chmod +x /usr/local/bin/docker-compose
```

**2. Dploy WordPress with Docker-compose
```
$ curl -sSL https://raw.githubusercontent.com/bitnami/bitnami-docker-wordpress/master/docker-compose.yml > docker-compose.yml
$ docker-compose up -d
```
**Then, open web browser and access *localhost* to see result**
<img src="./pr2_result.png">