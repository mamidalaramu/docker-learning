## Introduction to Docker Commands:

Docker provides a set of powerful commands for managing containers and images. In this README, we'll explore some of the most commonly used Docker commands and their functionalities.

## Docker Start:

The `docker start` command is used to start one or more stopped containers. It takes the container ID or name as an argument and brings the container back to a running state.

docker start <container-id>

## Docker Run:

The `docker run` command is used to create and start a new container based on a specified image. It can also be used to run commands inside a container. Here's the basic syntax:

docker run [OPTIONS] IMAGE [COMMAND] [ARG...]

Some common options include:
- `-d`: Run the container in detached mode (background).
- `-it`: Start the container in interactive mode, allowing you to interact with the container's shell.
- `-p`: Publish container's ports to the host.
- `-v`: Mount a volume from the host to the container.

## Docker Stop:

The `docker stop` command is used to stop one or more running containers. It sends a SIGTERM signal to the container, allowing it to shut down gracefully.

docker stop <container-id>

## Interactive Mode (-it):

The `-it` flag is used with the `docker run` command to start a container in interactive mode. This allows you to interact with the container's shell and execute commands inside the container.

docker run -it <image-name>

## Detach Mode:

The `-d` flag is used with the `docker run` command to start a container in detached mode, meaning it runs in the background without attaching your terminal to it. This is useful for long-running processes or services.

docker run -d <image-name>

## Attach Mode:

The `docker attach` command is used to attach your terminal to a running container, allowing you to interact with processes running inside the container.

docker attach <container-id>

## Docker Remove:

The `docker rm` command is used to remove one or more containers from your system. It takes the container ID or name as an argument.

docker rm <container-id>

!NOTE: We cant remove a running container. first we need to stop and then remove it.

## Docker Prune:

Docker system prune reemoves all stopped containers, unused networks, dangling images, and build cache.

docker system prune

## Remove stopped containers automatically

docker run --help // to get more commands which we can use with run

docker run -p 8080:80 -d --rm <image-id>
-p map port
-d detach mode
--rm remove

docker stop <container name> // this will stop the container and removes it.

## Copy a file or folder after the docker image is created and is running
docker cp /path/to/folder_or_file containerID:/destination/path

if the path is not present in the docker container, it will be created by the docker.

## Naming Containers

You can give names to your Containers and Images  using the `--name` flag while creating them.

#naming a container

docker run -name <name> <image_id>

to stop and start using name

docker stop <name>
docker start <name>

## Naming Image

docker tag <source-image> <alias-name>:<tag>



These Docker commands are essential for managing containers and images effectively. Experiment with them to gain a better understanding of Docker's capabilities.
