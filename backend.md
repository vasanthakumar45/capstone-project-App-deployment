Task 5: Docker Hub
-------------------

Create two repositories named "dev" and "prod" on Docker Hub to push images. The "Prod" repository must be private, while the "dev" repository can be public.

Use the following commands to execute the Bash scripts:

./build.sh   # To build the Docker image

./deploy.sh <target>   # Here, 'target' refers to 'dev' or 'prod' on Docker Hub to push the image to the respective repository
Example usage:


./deploy.sh dev   # Docker image is pushed to the dev repository on Docker Hub

./deploy.sh prod   # Docker image is pushed to the prod repository on Docker Hub

![image5](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/76d5188b-430c-4b1e-99fd-80e37aacc196)

-----------------------------------------------------------------------------------------------------------------------------------------

Task 6: Jenkins Installation
---------------------------

Install Jenkins on Ubuntu on my local machine.

Steps to Install Jenkins:

Install Jenkins on Ubuntu:

![image7](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/2f6d30ef-9225-4cca-a432-e573388bb81e)

After installing Jenkins, navigate to our browser and type localhost:8080 to access the Jenkins login page.

![image8](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/478dbe11-7ece-4756-bbdd-5d0ebfcb606f)

Enter our username and password, and complete the setup steps. Then, i have created two Jenkins jobs named 'dev' and 'prod'.

![image9](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/2b152e9b-7914-44e9-8d7e-c021970bd794)

Configure Jenkins Jobs for Auto Build Trigger:

Under Job Configuration:

Source Code Management: Choose Git and add your repository. Select the appropriate credentials.

Branches to Build: Choose */dev.

![image11](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/727b2835-8e75-46cb-a8f2-28e6e5e27348)

![image12](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/02b34d14-ecf3-4844-86e9-c380f7245df8)


Build Triggers: Enable GitHub hook trigger for GITScm polling.

![image13](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/f40ef93d-5974-4b6f-8a42-8ba7274f51ae)

Build Steps: Select execute shell and specify the script.

![image14](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/b7b35d3c-8dea-41a0-a70d-b55813765008)

After creating the pipeline, save it, and trigger the build to ensure everything works properly.

![image10](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/47afb4cb-94dd-4a6b-911a-48d5fa8c1ccd)

![image15](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/f31d8e70-169d-47d9-91c2-85e50db64ace)


After the pipeline is successfully created, review the console output.

![image16](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/d5d9d1bf-d7a2-4911-bedb-0528f16a105f)

Successfully create the 'prod' job and verify the output below.

![image17](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/7ed427ec-0d24-4e6f-9626-1d4ad96276f7)


The Docker image is successfully pushed to our Docker Hub account in the "dev_repo" and "prod_repo". The output is given below

![image18](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/6352e7d2-0b27-4af3-ad50-6f9d7ae9c1af)

![image19](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/9ac433a7-f4a8-4219-b015-630b64182f98)

--------------------------------------------------------------------------------------------------------------------------------
Task 7 : AWS
------------

Launch a t2.micro instance and deploy the created application \

Configure SG as below: \

Whoever has ip address can access the application
login to server should be made from my ip address

![image20](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/7c9da6d0-7688-45ef-a599-4ac7ad81140e)


Following security inbound rules as mentioned in above requirements and launch an instance

![image21](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/fa5aa0fe-7be6-4f05-b237-0fe908848cf8)

Connect to EC2 instance connect by clicking on Connect , a new tab opened with ssh connection terminal, output image is given below

![image22](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/0165df5c-dd58-4dab-83af-7237ad31893f)











