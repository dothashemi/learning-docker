# Golden Food Simple Coming Soon Page

## with Docker Compose

### 1. Make and Run the Container
```
docker-compose up -d

docker ps
```

### 2. Copy the Sources
```
sudo cp src/* /var/lib/docker/volumes/gf-vol/_data
```

## with Docker Commands
### Using GF Image
```
docker build -t goldenfood:latest --no-cache .

docker run --name gf-web --rm -d -p 80:80 goldenfood
```
### Using Bind Mounts
```
docker run --name goldenfood --rm -d -p 80:80 -v $(pwd)/src:/usr/local/apache2/htdocs httpd
```

## Reverse Proxy
We can use nginx as a reverse proxy to pass traffic to the container; instead of port mapping or when we deploy multiple websites on a server.