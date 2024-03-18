Version Control
-----------------

Now we have all the deployments done , let's push our code to our git repository where we can store and make necessary changes to source code in real-time.

*Initialize git repo locally using  git init

  * Add our files to the repo using  -->  git add .
  
  * commit our changes to the repo with message using -->  git commit -m "Initial commit"
    
  * Add a remote repo , here I have used as origin --> git remote add origin <my github-url>
  
  * push to dev branch using -->  git push origin dev
    
  * Also push entire source code to master branch to get a realtime deployment feel of project  -->   git push origin master

![image5](https://github.com/vasanthakumar45/capstone-project-App-deployment/assets/154395432/dc284ed5-2718-4132-b3d1-1822261cc5f1)

    
  * Later in project if a developer makes changes in dev , i.e, adding features , it can be merged in master branch on proper approvals and tests
    
  * We can see both branches with source code in our github repo as shown below

