# Persist data in Docker containers

## Introduction

Docker containers are ephemeral by design. This means that any data stored inside a container is lost when the container is stopped or removed. To persist data between container restarts, you can use Docker volumes.

In this guide, you will learn how to persist data in Docker containers using volumes. We will cover the following topics:

- Creating a Docker volume
- Using volumes in Docker containers
- Using volumes in Docker Compose

## Creating a Docker volume

A Docker volume is a directory on the host machine that is mounted into a container. This allows you to persist data 
between container restarts. 

To create a Docker volume, you can use the `docker volume create` command. For example, to create a volume named `myvolume`, you can run the following command:

```shell
docker volume create myvolume
```

You can list all the volumes on your system using the `docker volume ls` command:

```shell
docker volume ls
```

To remove a volume, you can use the `docker volume rm` command. For example, to remove the `myvolume` volume, you can run the following command:

```shell
docker volume rm myvolume
```

## Using volumes in Docker containers

To use a volume in a Docker container, you need to specify the volume when running the container. You can do this using the `-v` flag. For example, to mount the `myvolume` volume into a container named `mycontainer`, you can run the following command:

```shell
docker run -v myvolume:/path/in/container mycontainer
```

This will mount the `myvolume` volume into the `/path/in/container` directory inside the `mycontainer` container.

> [!IMPORTANT]
You can also use volumes in a `docker-compose.yml` file. For example, the following `docker-compose.yml` file mounts the `myvolume` volume into a container named `mycontainer`:

> Make sure to create the volume before running the `docker-compose` command.
```yml
services:
  mycontainer:
    image: myimage
    volumes:
      - myvolume:/path/in/container
  
volumes:
  myvolume:
```

This will mount the `myvolume` volume into the `/path/in/container` directory inside the `mycontainer` container.
The path will be created automatically if it does not exist. For example, a volume path for database data could look like this:

```yml
services:
  db:
    image: postgres
    volumes:
      - db_data:/var/lib/postgresql/data
```


> [!RECOMMENDATION]
> This is the clearest way to persist data in Docker containers. It is recommended to use a Docker Compose, 
> especially in case of a multi-container application.


> For more information on creating a docker compose, Check out the [Docker Compose Guide](docker-compose-guide.md)!

