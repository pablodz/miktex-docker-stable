# miktex-docker-stable

Docker Image to run tex files anywhere with miktex based on Ubuntu 20.04 and working on Linux/Windows/MacOS

## Install


```bash
docker pull pablogod/miktex-safe
```

```bash
docker build --tag pablogod/miktex-safe .
```


## Create volume

```bash
docker volume create --name miktex
```

## Run Docker

```bash
docker run --rm -ti \
  -v miktex:/miktex/.miktex \
  -v $(pwd):/miktex/work \
  -e MIKTEX_GID=$(id -g) \
  -e MIKTEX_UID=$(id -u) \
  pablogod/miktex-safe \
  pdflatex main.tex

```
