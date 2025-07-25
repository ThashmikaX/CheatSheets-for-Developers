---
title: Docker CheatSheet
description: The most commonly used docker commands are given here.
created: 2022-10-22
---

## Table of Contents

- [Docker CheatSheet for Developers](#docker-cheatsheet-for-developers)
  - [Run a New Container](#run-a-new-container) 
  - [Manage Containers](#manage-containers)
  - [Manage Compose](#manage-compose)
  - [Manage Images](#manage-images)
  - [Manage System](#manage-system)
  - [Info and Stats](#info-and-stats)

# Docker CheatSheet for Developers

## Run a new Container

| Command                                        | Description                              |
| ---------------------------------------------- | ---------------------------------------- |
| `docker run IMAGE`                             | Start A New Container from an image      |
| `docker run --name CONTAINER IMAGE`            | Assign a name                            |
| `docker run -p HOSTPORT:CONTAINERPORT IMAGE`   | Map a Port                               |
| `docker run -P IMAGE`                          | Map All ports                            |
| `docker run -d IMAGE`                          | Start Container in Background            |
| `docker run --hostname HOSTNAME IMAGE`         | Assign a Hostname                        |
| `docker run --add-host HOSTNAME:IP IMAGE`      | Add a dns entry                          |
| `docker run -v HOSTDIR:TARGETDIR IMAGE`        | Map a local Directory into the Container |
| `docker run -it --entrypoint EXECUTABLE IMAGE` | Change the Entrypoint                    |

**[🔼Back to Top](#table-of-contents)**

## Manage Containers

| Command                                | Description                              |
| -------------------------------------- | ---------------------------------------- |
| `docker ps`                            | Show a list of running containers        |
| `docker ps -a`                         | Show a list of all containers            |
| `docker rm CONTAINER`                  | Delete a container                       |
| `docker rm -f CONTAINER`               | Delete a running container               |
| `docker CONTAINER prune`               | Delete stopped containers                |
| `docker stop CONTAINER`                | Stop a running container                 |
| `docker start CONTAINER`               | Start a stopped container                |
| `docker cp CONTAINER:SOURCE TARGET`    | Copy a file from a container to the host |
| `docker cp TARGET CONTAINER:SOURCE`    | Copy a file from the host to a container |
| `docker exec -it CONTAINER EXECUTABLE` | Start a shell inside a running container |
| `docker rename OLD_NAME NEW_NAME`      | Rename a container                       |
| `docker commit CONTAINER`              | Create an image out of a container       |

**[🔼Back to Top](#table-of-contents)**

## Manage Compose

| Command                                                                     | Description                              |
| --------------------------------------                                      | ---------------------------------------- |
| `docker compose build --no-cache`                                           | Build docker compose with no-cache       |
| `docker compose ls`                                                         | Show a list of running compose           |
| `docker compose up -d --force-recreate`                                     | Down and again up existing compose       |
| `docker-compose --env-file .env.server --env-file .env up -d --build`                                     | Up docker compose with env file       |
| `docker compose -p <project_name> down`                                     | Down compose from any directory          |
| `docker-compose -f docker-compose.yml -f docker-compose.traefik.yml up -d`  | Up docker compose with custom overide file(default overide will not effect) |         |

**[🔼Back to Top](#table-of-contents)**

## Manage Images

| Command                           | Description                              |
| --------------------------------- | ---------------------------------------- |
| `docker pull IMAGE[:TAG]`         | Download an image                        |
| `docker push IMAGE`               | Upload an image to a repository          |
| `docker rmi IMAGE`                | Delete an image                          |
| `docker images`                   | Show list of all images                  |
| `docker image prune`              | Delete dangling images                   |
| `docker image prune -a`           | Delete all unused images                 |
| `docker build DIRECTORY`          | Build an image from a Dockerfile         |
| `docker tag IMAGE NEWIMAGE`       | Tag an image                             |
| `docker build -t IMAGE DIRECTORY` | Build and tag an image from a Dockerfile |
| `docker save IMAGE > FILE`        | Save an image to a .tar file             |
| `docker load -i TARFILE`          | Load an image from a .tar file           |

**[🔼Back to Top](#table-of-contents)**

## Manage System

| Command                           | Description                              |
| --------------------------------- | ---------------------------------------- |
| `docker system prune --all --force` | Removes everything that is not in use  |
| `docker builder prune` | Removes build cache  |
| `docker container prune` | Remove stopped containers  |
| `docker network create traefik-public` | Create docker network named "traefik-public"  |

**[🔼Back to Top](#table-of-contents)**

## Info and Stats

| Command                 | Description                            |
| ----------------------- | -------------------------------------- |
| `docker logs CONTAINER` | Show the logs of a container           |
| `docker stats`          | Show stats of a running container      |
| `docker top CONTAINER`  | Show processes of a container          |
| `docker version`        | Show installed docker version          |
| `docker inspect NAME`   | Get detailed info about an object      |
| `docker diff CONTAINER` | Show all modified files in a container |
| `docker port CONTAINER` | Show mapped ports of a container       |
| `docker system df`      | Show storage usage in docker           |

**[🔼Back to Top](#table-of-contents)**

