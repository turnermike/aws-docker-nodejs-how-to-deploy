# How to Deploy a Node.js Application to Amazon Web Services Using Docker
Tutorial: [https://www.zeolearn.com/magazine/how-to-deploy-a-node.js-application-to-amazon-web-services-using-docker](https://www.zeolearn.com/magazine/how-to-deploy-a-node.js-application-to-amazon-web-services-using-docker)
Source code: [https://github.com/emmyyusufu/sample-nodejs-app](https://github.com/emmyyusufu/sample-nodejs-app)

# Docker

Build container:
`docker build -t aws-docker-nodejs .`

Run the new container for the first time:
`docker run -p 80:3000 --name aws-docker-nodejs <image_id>`

Run an existing container:
`docker start aws-docker-nodejs`

Stop container:
`docker stop aws-docker-nodejs`

# AWS Container Registry
Tag and push the image to ECR.

Login:
`$(aws ecr get-login --no-include-email --region ca-central-1)`

Build the Docker image:
`docker build -t aws-docker-nodejs .`

Tag the image so it can be pushed to ECR:
`docker tag aws-docker-nodejs:latest 724588555329.dkr.ecr.ca-central-1.amazonaws.com/aws-docker-nodejs:latest`

Push the image to the repository:
`docker push 724588555329.dkr.ecr.ca-central-1.amazonaws.com/aws-docker-nodejs:latest`