
# docker-amstrad-crossdev
Docker file to install various tools needed for Amstrad CPC crossdev

## Linux

### Installing docker (need to verify)
```bash
$ sudo apt-get install docker.io
$ sudo useradd docker $USER 
```


### Pulling our image

```bash
$ docker pull cpcsdk/crossdev
```


### Or building yourself the image

```
$ docker build -t cpcsdk/crossdev .
```

Please note that there is a specific branch when using the image on a raspberrypi (`raspbian-stretch`).

## Windows

The aim of Docker is to manipulate Linux containers. It is of course totally incompatible with Windows world !
However, it is possible to use it thanks to Linux virtual machines...

### Installation of Docker

Follow the instructions there: https://docs.docker.com/engine/installation/windows/

Otherwise :

  1. Download Docker Toolbox https://github.com/docker/toolbox/releases/download/v1.9.1/DockerToolbox-1.9.1.exe
  2. Install it and follow the instructions  
  
  


###  building yourself the image

Launch Git bash:

You have to manually build and tag the container under windows.
It seems to use a container built under Linux may cause issues.

```
$ cd <folder_with_Dockerfile>
$ docker build -t cpcsdk/crossdev .
$ docker tag cpcsdk/crossdev:latest cpcsdk/crossdev:3.1
```

The container can be tested by using:

```
$ winpty docker run --rm=true -i -t cpcsdk/crossdev
```
