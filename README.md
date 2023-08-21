# Introduction to CI/CD on AWS
In this project, you will learn how to configure ci/cd pipeline on aws. 
The pipeline set up will be done using cloudformation. So in the process of understanding how to create a deployment     pipeline, you will also horn your Cloudformation skill. We will be using both Github and Codecommit as our code source.  
The repo you cloned contains the following files:
- template.yml
- buildspec.yml
- README.md 
- index.html 
Each of the files will be used in this project.
### Follow the steps below carefully to set up your first pipeline on aws:
#### STEP 1: Repo set up (GitHub As Source)
1. Go to your Github repository and create a new repo.
2. Leave the repo empty.
3. Follow the steps mentioned in this [video](https://www.youtube.com/watch?v=toFrROIhUHM) to create a personal access token.
4. Take note of the personal access token, your repo name and your github username because you will need them in subsequent steps.
#### STEP 2: Deploy pipeline with Cloudformation
1. Access your aws account and search for Cloudformation in the search box.
2. Create a new stack on Cloudformation.
3. Select the option to upload a template file and upload the **template.yml** file in this folder.
4. Input the required parameters **see STEP 1** and create the stack.
#### STEP 3: Push to the pipeline
1. Open the new repo you created in **STEP 1**
2. Add the **index.html** and **buildspec.yml** files in the current folder to the repo.
3. Commit the changes to main. 
4. Search for Codepipeline in aws console search box to see how the deployed code goes through the pipeline stages.
#### STEP 4: View Changes
1. Locate and click on the bucket that ends with **-website-bucket** in S3.
2. Click on the bucket properties and locate **static website hosting**.
3. Click on the url provided to see the content of the index.html page we pushed to the pipeline.
#### STEP 5: Push new update.
1. Change the content of the index.html file to whatever you want and push the update to main.
2. Navigate to aws Codepipeline dashboard to see how the new push to main triggered the pipeline.
3. Once the pipeline runs successfully, go back to S3 and click on the static website url to see the new update.
#### STEP 6: Repo set up (Codecommit As Source)
1. In the **template.yml's** Resources section, uncomment both the "Repository" and "SNSRepoTrigger" resources.
2. Scroll down to the Codepipeline Resource in **template.yml** file and comment out the "GithubSource" and uncomment the "Codecommit" Source.
3. Save the changes.
#### STEP 7: Update the Cloudformation stack
1. Navigate to the Cloudformation dashboard on aws console and click on the stack we created in **STEP 2**
2. Update the stack with the updated **template.yml** file.
3. When the update completes, go to the Codepipeline dashboard to confirm that the pipeline source stage is now using Codecommit.
#### STEP 8: Add files to Codecommit Repo
1. Navigate to aws Codecommit dashboard on the console and locate the repository we just created.
2. Click on the repository and add the **index.html** and **buildspec.yml** files.
3. Commit the changes to main.
4. Go to the pipeline to see the effect of the push we made on Codecommit.
#### STEP 9: View Changes
1. Navigate to the S3 console and find the bucket that was used to deploy our application.
2. Locate the static webiste url of the bucket in the properties section of the bucket.
3. Click on the url to see the simple website again.

You can repeat **STEP 5** to have feel of how changes to Codecommit updates the website.