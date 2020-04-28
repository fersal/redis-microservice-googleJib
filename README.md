# Cache-Service-Image

This Project does not require Docker to be installed nor does it use a Dockerfile.\
Instead, [Google's Jib](https://cloud.google.com/blog/products/gcp/introducing-jib-build-java-docker-images-better) provides
Gradle integration and a way to create an image without a Docker instance using Google's format which is
Docker compatible. The image then is pushed to ECR repository or local Docker instance.

###  Google Jib
* Upon creating image it publishes to desired registry. Executing **./gradlew jib** you have to provide AWS ECR repository name;
 executing **./gradle jibDockerBuild** publishes to local Docker running instance.
* How to configure Amazon Credential Helper (need brew): https://github.com/awslabs/amazon-ecr-credential-helper#Configuration
    * use "credHelpers": {
                "aws_account_id.dkr.ecr.region.amazonaws.com": "ecr-login"
            }

### Create Image using Jib
>build and publish image to AWS ECR with ECR credential helper 
* ./gradlew jib

>build image a nd publish to local Docker using Docker 
* /gradlew jibDockerBuild
 
