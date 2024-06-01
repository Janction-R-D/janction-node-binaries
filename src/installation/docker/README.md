# Janction Node Docker Image

Preconfigured Docker image for running a Janction Node. The Docker Compose setup requires python3.

## Usage

```sh
docker run -it \
  -e mysql_host=<HOST> \
  -e mysql_port=<PORT> \
  -e mysql_user=<USER> \
  -e mysql_pass=<PASSWORD> \
  -e mysql_db=<DBNAME> \
  janction/janction-node:latest
```

### Example usage

```sh
docker run -it \
  -e mysql_host=host.docker.internal \
  -e mysql_port=3306 \
  -e mysql_user=janction-user \
  -e mysql_pass=janction2Pass \
  -e mysql_db=janction \
  janction/janction-node:latest
```

## Docker Compose

```sh
docker-compose up
```

This will start Janction-Node-Binaray, Mysql and Install Python3 environment in Docker and create persistent
data directories for mysql in `./data/mysql`. You
can access these via:

- Mysql:
  - `mysql://janction:pass@localhost:3306/janction`


Once this is up and running, you can use
[`janction-cli`](https://github.com/Janction-R-D/janction-cli) to start your tasks.

> **Important** Increase memory limits for the docker engine running on your machine. Otherwise docker build command will fail due to out of memory error. To do that, open docker-desktop and go to Resources/advanced/memory.
# Remove the original image
```
docker rmi janction/janction-node:latest

```