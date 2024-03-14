## Docker Cheat Sheet

I've added a Docker cheat sheet in PDF format to this repository from docker website. This cheat sheet provides a quick reference guide to common Docker commands, options, and best practices.

## Introduction to Docker:

Docker is a platform that allows you to develop, deploy, and run applications inside containers. Containers are lightweight, portable, and self-sufficient environments that package everything needed to run an application, including code, runtime, libraries, and dependencies.

## What is an Image?

In Docker, an image is a lightweight, standalone, executable package that includes all the necessary components to run a piece of software. Images serve as the basis for containers. They are built from a Dockerfile, which contains instructions for assembling the image.

## What is a Container?

A container is a runtime instance of an image. It encapsulates an application along with its dependencies and runs in isolation from other containers and the host system. Containers provide consistency across different environments and ensure that applications run reliably, regardless of the underlying infrastructure.

## About the Dockerfile:

The provided Dockerfile is used to build a Docker image for a Node.js application. It contains the following instructions:

1. FROM node: Specifies the base image as the official Node.js image from Docker Hub.
2. WORKDIR /app: Sets the working directory inside the container.
3. COPY package.json /app: Copies the package.json file from the host machine to the working directory in the container.
4. RUN npm install: Installs dependencies defined in package.json.
5. COPY . /app: Copies the rest of the application files from the host machine to the working directory in the container.
6. EXPOSE 80: Exposes port 80 on the container to allow communication with the Node.js application.
7. CMD ["node", "server.js"]: Defines the command to run the Node.js server when the container starts.

## Building the Image
Use docker build command to build the image

docker build .

. is used to  specify that we are building in the current directory, which contains our Dockerfile.

## Exposing Ports:

To expose port 80 and allow external access to the Node.js application, you need to map port 80 of the container to a port on the host machine. This is done using the -p flag when running the container:

docker run -p 8080:80 <image-name>

In this example, port 80 of the container is mapped to port 8080 on the host machine. You can replace 8080 with any available port on your system.

## Docker Pull:
docker pull command pulls an image or a repository from a registry from Docker hub.

docker pull <image-name>

## Basic Docker Commands:

Here are some basic Docker commands to manage containers and images:

- To list all images:
docker images
- To list all containers (including stopped containers):
docker ps -a
- To start a container:
docker start <container-id>
- To stop a container:
docker stop <container-id>
- To start a container in interactive mode (-it):
docker run -it <image-name>
- To check if containers are running:
docker ps
- To list all containers
docker ps -a
- To remove an unused image:
docker rmi <image-id>
- To remove a stopped container:
docker rm <container-id>



These commands should help you get started with Docker and manage your containers and images effectively.

