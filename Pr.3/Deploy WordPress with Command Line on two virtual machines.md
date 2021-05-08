# Practice 3
---
## Requirements:
```
• Create two Ubuntu virtual machines
• Setup Docker inside VMs
• Deploy WordPress with Command Line on two virtual machines

```
---
## Guide
Create one more Virtual Machine and setup Docker inside this VMs
**1. On VM 1**
- Create mariadb volume
```
$ sudo docker volume create --name mariadb_data
```
Run and connect MariaBD with network
$ sudo docker run -d --name mariadb \
    --env ALLOW_EMPTY_PASSWORD=yes \
    --env MARIADB_USER=bn_wordpress \
    --env MARIADB_PASSWORD=luong123 \
    --env MARIADB_DATABASE=bitnami_wordpress \
    --network wordpress-network \
    --volume mariadb_data:/bitnami/mariadb \
    bitnami/mariadb:latest
```
**1. On VM 2**
- Create Wordpress Volume and connect it to network
```
$ sudo docker volume create --name wordpress_data
$ sudo docker run -d --name wordpress \
    -p 8080:8080 -p 8443:8443 \
    --env ALLOW_EMPTY_PASSWORD=yes \
    --env WORDPRESS_DATABASE_USER=bn_wordpress \
    --env WORDPRESS_DATABASE_PASSWORD=bitnami \
    --env WORDPRESS_DATABASE_NAME=bitnami_wordpress \
    --network wordpress-network \
    --volume wordpress_data:/bitnami/wordpress \
    bitnami/wordpress:latest

```
**Then, open web browser and access local to see result**

<img src="./pr3_result.png">