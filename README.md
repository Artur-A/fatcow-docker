# Docker development environment for FatCow provider


This is not a 1 to 1 equivalent of the environment. FatCow uses obsolete Ubuntu 12 with custom compiled PHP 5.5 and 7.1.

The settings are made as close as possible to mimic the environment: Ubuntu 16, Apache, PHP 7.1 with similar enabled features.

### Example of usage
Create `html` folder with the site content, add `docker-compose.yml` to the root directory.

```
docker-compose.yml
├── html/
|  ├── index.php    
```

`docker-compose.yml`:
```
version: '3'
services:
  php:
    image: aartur/fatcow-php:7.1
    ports:
        - "8080:8080"
    volumes:
      - ".:/var/www/html"
    networks:
      - frontend
networks:
  frontend:
```


Run `docker-compose up` in the terminal and open `http://localhost:8080`.

Some docker images are based on https://hub.docker.com/r/1and1internet/