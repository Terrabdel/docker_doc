# Docker_doc

# Run 101 tutorial

$ docker run --name repo alpine/git clone https://github.com/docker/getting-started.git & docker cp repo:/git/getting-started/ .

$ cd getting-started & docker build -t docker101tutorial .

$ docker run -d -p 80:80 --name docker-tutorial docker101tutorial

# Basics

## List containers

$ docker ps

$ docker ps -a # --all

## List images

$ docker image ls

## Run container

$ docker run -di --name {} image_name # -di = detached & interactif, --name = specify container name

## Connect to a container

$ docker exec -ti container_name sh (bash is better) # for -ti option https://stackoverflow.com/questions/30137135/confused-about-docker-t-option-to-allocate-a-pseudo-tty

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

# Volumes

## Mount volumes

It serves to keep a folder from the machine synchronized with a folder in the container.

$ docker run -v local_directory_path:containter_directory_path

## Volumes doc
  
Usage:  docker volume COMMAND  
  
Manage volumes  
  
Commands:  
&nbsp;&nbsp;&nbsp; create &nbsp;&nbsp;  Create a volume  
&nbsp;&nbsp;&nbsp; inspect &nbsp;&nbsp; Display detailed information on one or more volumes  
&nbsp;&nbsp;&nbsp; ls &nbsp;&nbsp;  List volumes  
&nbsp;&nbsp;&nbsp; prune &nbsp;&nbsp;  Remove all unused local volumes  
&nbsp;&nbsp;&nbsp; rm &nbsp;&nbsp; Remove one or more volumes  
  
  ## Create volume

  $ docker volume create volume_name

  ## Inspect volume

  $ docker volume inspect volume_name

  ## Run Docker with a specified volume

  $ docker run (-tid --name container_name -p xxxx:xxxx) --mount source=volume_name, target=containter_directory_path image_name

  ## Delete a volume

  $ docker volume rm volume_name (must be not used in a container)


  # Environment variables

  ## To-Do
