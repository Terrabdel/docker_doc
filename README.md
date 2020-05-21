# Docker_doc

# Basics

## Show containers

$ docker ps

$ docker ps -a # --all

## Run container

$ docker run -di --name {} image_name # -di = detached & interactif, --name = specify container name

## Connect to a container

$ docker exec -ti image_name sh (bash is better) # for -ti option https://stackoverflow.com/questions/30137135/confused-about-docker-t-option-to-allocate-a-pseudo-tty

## Run nginx (example)

$ docker run -tid -p 8080:80 --name web nginx:latest # -p for port maping, map container port 80 into machine port 8080, :latest for the latest version

## Inspect container

$ docker inspect conainer_name # (for example web from last command)

## Start an exited container (after restarting docker for example)

$ docker start conainer_name

## Stop a container

$ docker stop conainer_name

## Delete a container

$ docker rm -f container # -f forcing even the container is running

## Specify volumes

It serves to keep a folder from the machine synchronized with a folder in the container.\n 
$ docker run -v local_directory_path:containter_directory_path