inetsys-ubuntu
===================

Contains a recipe for making a [Docker](http://docker.io) container with Ubuntu 12.04, updated so far, with additional packages:

- Wget
- Python (with setup tools, easy_install)
- Supervisor

Build with Docker [installed](http://www.docker.io/gettingstarted/).

## Install docker:
```
sudo apt-get -y install lxc-docker
curl get.docker.io | sudo sh -x
```

## Installation

```
$ git clone git@github.com:inetsys/docker-ubuntu.git
$ cd docker-ubuntu
$ sudo docker build -t="docker-ubuntu" .
```

## Supervisor

You can derive a new image including services (such as Apache, nginx, MySQL, ...) using the supervisor daemon. There's an example file on how to include them in the supervisor.conf file

This file must be placed in /etc/supervisor.conf, it can be added to the Dockerfile with add

```
ADD ./supervisor.conf /etc/supervisor.conf
```

## And run the container, for example with bash prompt:
```
sudo docker run -i -t docker-ubuntu
```

## License
MIT