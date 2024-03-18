Task 5: Docker Hub
-------------------

Create two repositories named "dev" and "prod" on Docker Hub to push images. The "Prod" repository must be private, while the "dev" repository can be public.

Use the following commands to execute the Bash scripts:

bash
Copy code
./build.sh   # To build the Docker image
./deploy.sh <target>   # Here, 'target' refers to 'dev' or 'prod' on Docker Hub to push the image to the respective repository
Example usage:

bash
Copy code
./deploy.sh dev   # Docker image is pushed to the dev repository on Docker Hub
./deploy.sh prod   # Docker image is pushed to the prod repository on Docker Hub
image5

Task 6: Jenkins Installation

Install Jenkins on Ubuntu on my local machine.
Steps to Install Jenkins:

Install Jenkins on Ubuntu:

image7

After installing Jenkins, navigate to your browser and type localhost:8080 to access the Jenkins login page.

image8

Enter your username and password, and complete the setup steps. Then, create two Jenkins jobs named 'dev' and 'prod'.

image9

Configure Jenkins Jobs for Auto Build Trigger:

Under Job Configuration:

Source Code Management: Choose Git and add your repository. Select the appropriate credentials.
Branches to Build: Choose */dev.
image11
image12

Build Triggers: Enable GitHub hook trigger for GITScm polling.
image13

Build Steps: Select execute shell and specify the script.
image14

After creating the pipeline, save it, and trigger the build to ensure everything works properly.

image10
image15

After the pipeline is successfully created, review the console output.

image16

Successfully create the 'prod' job and verify the output.

image17

The Docker image is successfully pushed to our Docker Hub account in the "dev_repo" and "prod_repo".

image18
image19

These corrections aim to provide clear and concise instructions for each task. Let me know if you need further assistance or modifications!








