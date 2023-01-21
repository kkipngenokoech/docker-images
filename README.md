# docker-images

to run a docker image - `sudo docker run busybox`

## example of images

1. Alpine
2. busybox
3. node
4. ubuntu
5. Nginx
6. python postgres

## image and container

A container is a runtime instance of an image.

you can edit images on the containers

## docker-image commands

### sudo docker images

lists all images

### sudo docker image ls

also lists all images

### sudo docker image rm <image-id>

deletes a specific image

### sudo docker images prune -a

delete all images that are not linked ito containers

### sudo docker image inspect <image-id>

find out more information about an image

### sudo docker image history <image-id>

tells us the history about the layers that were built when the images were created

## layering in docker

layers are not editable

when you run an image, this image layers are run layers by layers

images are made up of multiple read only layers

multiple layers are typically based on the same image

when an image is instantiated into a container, a top writable layer is created which is deleted when the container is destroyed.

docker uses storage drivers to manage the contents of the image layers.

## docker image union file system

docker images are read only.

## docker file

we create images from the docker files.

this is a file that contains all the commands in order, needed to build a given image.

A dockerfile is executed by the docker build command

when you issue a docker build command that request is is sent to the docker daemon where the image is created

### docker file help

man dockerfile - commands that breaks down how a dockerfile can be used

man docker build - learn more about how to build images from a dockerfile

### docker file syntax

1. ADD - copies a file into an mage, but supports tar and remote url
2. COPY -  copies file into the image you are building
3. VOLUME -  creates a mount point as defined
4. ENTRYPOINT - the executable that is run when the container is run
5. EXPOSE -  documents the port that should be published when the image is used to create a container/ allows containers to be accessed from the outside
6. CMD
7. ENV
8. RUN - run a new command in a new layer
9. WORKDIR - define the working directory of the container
10. LABEL
11. FROM
12. MAINTAINER

### DOCKERFILE EXAMPLE

```dockerfile
#this is a sample image
FROM ubuntu
MAINTAINER kkipngenokoech@gmail.com
RUN apt-get update
RUN apt-get install nginx -y
CMD["ECHO","IMAGE CREATOR"]
```

to build this image you use the build image command: `docker build -t dockermultiverse .` - the last dot is necessary because you have to tell docker where it is creating from.

to create an image from it, you use `docker run <image-id>`

to get the image-id you run `docker images` then it will give you the id of the image

## docker registry

this is a place where we store our images(Docker Hub) - like github

it can be private ot public.
