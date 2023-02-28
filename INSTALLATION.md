# Installation
This document describes how to deploy your personal Rocketnotes installation in the cloud at AWS or on-premise on your own server.

### Prerequisites
The following tools need to be installed on your system prior to build and deploy to AWS or to your own infrastructure:

- [Node.js >= 14.x](https://nodejs.org/download/release/latest-v14.x/)
- [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)


First fork the repository, and then run the following commands to clone the repository locally.

```console
$ git clone https://github.com/{your-account}/rocketnotes.git
$ cd rocketnotes
$ npm install
```

## Cloud hosting
### Prerequisites
The following tools need to be installed on your system prior to build and deploy to AWS:

- [AWS CDK](https://github.com/aws/aws-cdk)

### Initial Setup
In order to deploy Rocketnotes at AWS you need an AWS Account and configure the AWS CLI locally with `aws configure` as usual.
The deployment itself is very straight forward.

But First, there need to be an existing Cognito user pool and a Hosted Zone associated with your AWS account in the region where you are going to deploy against.
You can create a Cognito user pool with a user domain and an app client with the aws console or also programmatically with the AWS CDK.
You find an example how to do it with the cdk here [example](asd).
If you want to create the cognito resources via the aws console, there are plenty of resources available how to do it. Here is a good [guide](ass) for example.

Second, you need an existing Hosted Zone in the target region of your AWS account. This requires a domain you are in charge of.
How to create a Hosted Zone and configure Route 53 as a DNS service with your domain you find [here](asfasf).

### Build
The Angular webapp need to be bundled in production mode.
The following environment variables are required for the production build:
```
$ export
```
Once your environment variables are specified run
```
cd webapp
npm install
npm run build
```

### Deploy
```console
$ cd cdk
$ cdk deploy
```
The first deployment will take some minutes, since all the resources and lambda functions need to be initially created.

## On-premise hosting
To be defined