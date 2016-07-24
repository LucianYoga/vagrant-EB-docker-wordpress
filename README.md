# Vagrant WordPress, RDS and Elastic Beanstalk

## Create custom wordpress docker image on Vagrant and push to ECR repository
1. install vagrant https://www.vagrantup.com/downloads.html
2. vagrant up
3. vagrant ssh
4. cd /src
5. In EC2 Container Service > Repositories, click Create repository.  Make sure the repository is in the same region as your EB environment.
4. Click View Push Commands and follow the instructions.
5. Update app/Dockerrun.aws.json "image" section to match fully qualified ECR image name.  Remember, image names in docker are fully qualified.  For example...

  `"image": "xxxxx.dkr.ecr.us-east-1.amazonaws.com/my-image-name:latest",`

## Create application zip file
  `cd app && zip -r ../v1.zip . --exclude .DS_Store`

## Upload to EB env and deploy
1. Click "Upload and Deploy"
2. Choose your zip file
3. Make sure Version label is a version label that hasn't been used before.
4. Click "Deploy"
