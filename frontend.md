Application Deployment

(Deploy the given react appliation to a production ready state)

Task 1: We need to clone the following repository and deploy the application on port 80 [HTTP]
Repo URL : https://github.com/sriram-R-krishnan/devops-build

* git clone https://github.com/vasanthakumar45/devops-build
  
root@Vasanth:~# ls
devops-build

root@Vasanth:~# cd devops-build/

root@Vasanth:~/devops-build# ls
build

root@Vasanth:~/devops-build# cd build

root@Vasanth:~/devops-build/build# ls

 asset-manifest.json      favicon.ico  index.html   logo512.png    robots.txt
_redirects  build     logo192.png  manifest.json  static


Task 2: Docker:

• Dockerize the application by creating a Dockerfile

• Create a docker-compose file to use the above image

we have createed Dockerfile and docker-compose file 

root@Vasanth:~/devops-build# vi Dockerfile

root@Vasanth:~/devops-build# cat Dockerfile

FROM node:14

WORKDIR /app

Run git clone https://github.com/vasanthakumar45/devops-build .

EXPOSE 80

CMD ["npx", "serve", "-s", "-l", "80", "build"]

root@Vasanth:~/devops-build# docker build -t app:v1 .

DEPRECATED: The legacy builder is deprecated and will be removed in a future release.
            Install the buildx component to build images with BuildKit:
            https://docs.docker.com/go/buildx/

Sending build context to Docker daemon  797.7kB

Step 1/5 : FROM node:14
 ---> 1d12470fa662
 
Step 2/5 : WORKDIR /app
 ---> Using cache
 ---> 51c5e49552d9
 
Step 3/5 : Run git clone https://github.com/vasanthakumar45/devops-build .
 ---> Using cache
 ---> f7f989dea2bb
 
Step 4/5 : EXPOSE 80
 ---> Running in d02e1a9e3209
Removing intermediate container d02e1a9e3209
 ---> 6022116a4dcf
 
Step 5/5 : CMD ["npx", "serve", "-s", "-l", "80", "build"]
 ---> Running in 5848c2722e27
Removing intermediate container 5848c2722e27
 ---> e394ea0e25e7
 
Successfully built e394ea0e25e7

Successfully tagged app:v1

root@Vasanth:~/devops-build# docker run -d -p 80:80 --name test app:v1

e206516e67b24a4767698046e7cd545453b41298c5e69a6f27bfb4fd6b5747d9

root@Vasanth:~/devops-build# docker images

REPOSITORY   TAG       IMAGE ID       CREATED          SIZE

app          v1        e394ea0e25e7   53 seconds ago   915MB

node         latest    1b9d5f3b36bf   2 weeks ago      1.1GB

node         14        1d12470fa662   10 months ago    912MB

root@Vasanth:~/devops-build# docker ps -a

CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS         PORTS                               NAMES

e206516e67b2   app:v1    "docker-entrypoint.s…"   3 minutes ago   Up 3 minutes   0.0.0.0:80->80/tcp, :::80->80/tcp   test

root@Vasanth:~/devops-build# vi docker-compose.yaml

root@Vasanth:~/devops-build# cat docker-compose.yaml

version: '3'

services:

  service1:
  
    image: app:v1
    
    container_name: test
    
    ports:
    
      - '80:80'


root@Vasanth:~/devops-build# docker-compose up -d

Creating test ... done

root@Vasanth:~/devops-build# docker-compose down

Stopping test ... done

Removing test ... done



root@Vasanth:~/devops-build# docker-compose up

Creating network "devops-build_default" with the default driver

Creating test ... done

Attaching to test



