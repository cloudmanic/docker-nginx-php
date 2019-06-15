# cloudmanic/nginx-php

Nginx and PHP built into the same image, run as non-root user.

Full Repo: https://github.com/cloudmanic/docker-nginx-php

A few goals for this docker image:

* Run the entire image as a local user, not as root. Hence Nginx runs on port 8080
* Bundle PHP into the image.

# Image Versions
 * PHP 7.2 - (https://github.com/cloudmanic/docker-nginx-php/tree/master/7.2)

# Example Docker Compose

```
version: "3"

services:
  web:
    image: cloudmanic/nginx-php:7.2

    user: "501:20"

    ports:
      - "80:8080"

    volumes:
      - ./:/www
      - ./web:/www/public
```
