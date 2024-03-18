Task 5 : Docker hub
--------------------

• Create 2 repos "dev" and "prod" to push images.
"Prod" repo must be private and "dev" repo can be public

Use following commands to execute bash scripts

./build.sh --- to build docker image

./deploy.sh <target> --- here targer refers to dev or prod of dockerhub so that image gets pushed to respective repository

./deploy.sh dev ---> docker image is pushed to my dockerhub account

./deploy.sh prod --->docker image is pushed to my dockerhub account

![image5](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/76d5188b-430c-4b1e-99fd-80e37aacc196)

----------------------------------------------------------------------------------------------------------------------------------------

Task 6 : Jenkins
-----------------

Jenkins Installation
-----------------------

Install Jenkins to insert of Ubuntu in my local machine.

Jenkins installed steps given below

![image7](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/2f6d30ef-9225-4cca-a432-e573388bb81e)

After installed jenkins--> Go to ou browser and type localhost:8080 -> I got a jenkins login page 

![image8](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/478dbe11-7ece-4756-bbdd-5d0ebfcb606f)

After enter username and password and done with some steps, we creating two jenkins jobs like 'dev' and 'prod'

![image9](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/2b152e9b-7914-44e9-8d7e-c021970bd794)

