# Introduction to CI/CD on AWS
In this project, you will learn how to configure ci/cd pipeline on aws. 
The pipeline set up will be done using cloudformation. So in the process of understanding how to create a deployment     pipeline, you will also horn your Cloudformation skill.
The repo you cloned contains the following files:
- template.yml
- buildspec.yml
- README.md 
Each of the files will be used in this project.
## Follow the steps below carefully to set up your first pipeline on aws:
### Repo set up
1. Go to your Github repository and create a new repo.
2. Leave the repo empty.
3. Follow the steps mentioned in this [video](https://www.youtube.com/watch?v=toFrROIhUHM) to create a personal access token.
4. Take note of the personal access token, your repo name and your github username because you will need them in subsequent steps.
### Deploy pipeline with Cloudformation
1. Go to your aws account and search for Cloudformation in the search box.
2. Create a new stack on Cloudformation.
3. Select the option to upload a template file and upload the template.yml file in this folder.
4. Input the required parameters and create the stack.