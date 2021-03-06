# deploy-laravel-multistage-build-docker

## Build images

Laravel
`docker build -t diltheyaislan/laravel:prod . -f Dockerfile`

Nginx
`docker build -t diltheyaislan/nginx:prod . -f Dockerfile.nginx`

## Create Docker network
`docker network create laranet`

## Create containers

Laravel
`docker run -d --network laranet --name laravel diltheyaislan/laravel:prod`

Nginx
`docker run -d --network laranet --name ngnix -p 8080:80 diltheyaislan/nginx:prod`