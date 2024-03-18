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

Now jenkins task to create auto build trigger from dev and master branch
---------------------------------------------------------------------------

under configuration -> source code management -> choose Git and add our repo here and select the credentials we've made earlier for github -> under Branches to build choose */dev

![image11](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/727b2835-8e75-46cb-a8f2-28e6e5e27348)

![image12](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/02b34d14-ecf3-4844-86e9-c380f7245df8)

Under build triggers enable GitHub hook trigger for GITScm polling

![image13](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/f40ef93d-5974-4b6f-8a42-8ba7274f51ae)

Under Build steps select execute shell and type the script

![image14](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/b7b35d3c-8dea-41a0-a70d-b55813765008)

After pipeline is created click save and do the Build now to check if everything is working properly or not

![image10](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/47afb4cb-94dd-4a6b-911a-48d5fa8c1ccd)

![image15](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/f31d8e70-169d-47d9-91c2-85e50db64ace)

After pipeline is successfull and console output is given below

![image16](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/d5d9d1bf-d7a2-4911-bedb-0528f16a105f)


I have also succesfully created prod job and screensshot is output is below

![image17](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/7ed427ec-0d24-4e6f-9626-1d4ad96276f7)

The docker image is succesfully pushed to our docker hub account in dev repo and prod repo its outpu omage is given below

![image18](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/6352e7d2-0b27-4af3-ad50-6f9d7ae9c1af)

![image19](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/9ac433a7-f4a8-4219-b015-630b64182f98)


