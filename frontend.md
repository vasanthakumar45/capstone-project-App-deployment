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

---------------------------------------------------------------------------------------------------------------------------------
Task 2: Docker
--------------

• Dockerize the application by creating a Dockerfile

• Create a docker-compose file to use the above image

we have createed Dockerfile and docker-compose file 

root@Vasanth:~/devops-build# vi Dockerfile

![image1](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/d363fc27-de9d-40aa-9441-5b9cd909813f)


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

![image2](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/ffb102f2-08ae-44fa-87cc-8c5f5ff3a3ec)

root@Vasanth:~/devops-build# docker-compose up -d

Creating test ... done


when we hit public Ipv4 address on port 80 we should see the application running on my browser

![image3](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/f2e21c87-9b40-4d83-8748-9616c7c4343d)

Hence we successfully deployed our app on port 80 with nginx and docker

----------------------------------------------------------------------------------------------------------------------------------------

Task 3 : Write 2 scripts
-------------------------


• build.sh - for building docker images

#!/bin/bash

echo "Running docker-compose build..."

docker-compose build

• deploy.sh - for deploying the image to server

![image4](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/030c8fe5-0ed2-4237-b711-503cb8c77a3e)

-----------------------------------------------------------------------------------------------------------------------------------------

Version Control
-----------------

Now we have all the deployments done , let's push our code to our git repository where we can store and make necessary changes to source code in real-time.

*Initialize git repo locally using  git init

  * Add our files to the repo using  -->  git add .
  
  * commit our changes to the repo with message using -->  git commit -m "Initial commit"
    
  * Add a remote repo , here I have used as origin --> git remote add origin <my github-url>
  
  * push to dev branch using -->  git push origin dev
    
  * Also push entire source code to master branch to get a realtime deployment feel of project  -->   git push origin master
    
  * Later in project if a developer makes changes in dev , i.e, adding features , it can be merged in master branch on proper approvals and tests
    
  * We can see both branches with source code in our github repo as shown below

![image5](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/dc284ed5-2718-4132-b3d1-1822261cc5f1)

