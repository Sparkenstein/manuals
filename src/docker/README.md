# Everything docker

## Installing Docker
### Ubuntu/Debian:
- Follow [this](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-18-04) link.


## Create image from dockerfile
- create Dockerfile
- run `docker image build -t image-name .`
- check if image is built with `docker image ls`
- run that image with `docker container run -p 5000:5000 --detach --name container-name image-name:image-tag`
- check containe with `docker ps`
