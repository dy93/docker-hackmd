[![](https://images.microbadger.com/badges/version/hackmdio/hackmd.svg)](https://microbadger.com/images/hackmdio/hackmd "Get your own version badge on microbadger.com") [![](https://images.microbadger.com/badges/image/hackmdio/hackmd.svg)](https://microbadger.com/images/hackmdio/hackmd "Get your own image badge on microbadger.com")

[![](https://images.microbadger.com/badges/version/hackmdio/hackmd:lite.svg)](https://microbadger.com/images/hackmdio/hackmd:lite "Get your own version badge on microbadger.com") [![](https://images.microbadger.com/badges/image/hackmdio/hackmd:lite.svg)](https://microbadger.com/images/hackmdio/hackmd:lite "Get your own image badge on microbadger.com")

docker-hackmd
===

Change
===
Forked from [https://github.com/hackmdio/docker-hackmd](https://github.com/hackmdio/docker-hackmd)
and use [https://github.com/dy93/hackmd](https://github.com/dy93/hackmd) to build docker image.
I use sqlite instead of postgres for easier backup.

## Prerequisite
* git
* docker (docker toolbox recommended)
* docker-compose (included in the docker toolbox)

See more here: https://www.docker.com/docker-toolbox

## Get started

1. Start you docker via `Docker Quickstart Terminal`, you will see a machine IP (remember that).
2. Run `git clone https://github.com/dy93/docker-hackmd.git`.
3. Run `docker-compose up` in your docker terminal.
4. Wait until see th log `HTTP Server listening at port 9999`, it will take few minutes based on your internet.
5. Open any browser and surf `<machine IP>:9999`

## Update

Start your docker and enter the terminal, follow below commands:

```bash
cd docker-hackmd ## enter the directory
git pull ## pull new commits
docker-compose pull ## pull new containers
docker-compose up ## turn on
```

## Backup
Just backup the _data_ folder

## Restore
Put the _data_ folder back

**Happy HackMD :smile:**
