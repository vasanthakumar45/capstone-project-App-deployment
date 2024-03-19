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

-------------------------------------------------------------------------------------------------------------------------------

Task 8 : Monitoring

• Setup a monitoring system to check the health status of the application. (Open-source)

* we have using cloud watch to check the health status of the application

* open cloud watch & click the matrics and copy the we create EC2 instance ID and paste to the cloud watch

* Enable to cpu utilization in cloud watch metrics state

![image23](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/2f59df7d-8079-4567-8f51-f1d83f47aada)

![image24](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/c675a05d-b96c-4bc8-b905-37ec57d15c2c)

In same page click and open All Alarm do configuration steps

![image25](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/4dc06bc7-5dff-4065-a628-807ceb81d158)

![image26](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/78742230-db0f-40bd-97e5-15db785a0b3f)

![image27](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/aa23dcf7-ee78-41df-92d6-07882fc472bf)

![image28](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/900eaee8-b541-409a-b976-b6833a592ee9)

![image29](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/9053bd05-57f1-4958-a0b1-e180f54bb9e3)

Check the wheather to cloud watch created Alarms 

![image30](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/6a81cbd9-0051-4504-81fb-c752b15ebbc2)

Open & connect our created EC2 machines and installed some steps for given below

![image31](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/dbfe5b4e-1eb9-42ae-98ab-ea02a9e019e5)

![image35](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/f4ffd37a-7082-42c5-9e28-081cd85e5e50)

![image32](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/6d91502a-da6d-4efb-a185-d8d724eca927)

 Sending notifications to our mail id. its wheather cheaking in cloud watch
 -----------------------------------------------------------------------------

 ![image33](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/365eaf0d-5022-483e-813c-d1c8ebd11fe4)
 
![image34](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/b34e1f81-a75b-476c-9f26-48f423334613)

 









