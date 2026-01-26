# 📦 Modular SAM + CodePipeline Project

This repository/folder contains a **modular, multi-file AWS SAM project** for the AWS Sensei Blog CI/CD Infrastructure.\
Infrastructure is split into multiple CloudFormation templates that are combined through a single `master.yaml`.\
This CodePipeline deploys for the AWS Sensei Blog the **SAM infrastructure** and the **Hugo static website** automatically.

------------------------------------------------------------------------

## 📁 Project Structure

    .
    ├── build                     
    │   └── codebuild.yaml          # CodeBuild project for Hugo site
    ├── foundation                     
    │   ├── artifacts.yaml          # S3 buckets and artifact storage
    │   └── roles.yaml              # IAM Roles (CodePipeline, CodeBuild, CloudFormation)
    ├── pipeline                     
    │   └── pipeline.yaml           # CodePipeline definition
    ├── master.yaml                 # Main SAM/CloudFormation entrypoint
    └── README.md                   # You're reading this    

------------------------------------------------------------------------

## 🚀 Deployment

## Deploy with SAM CLI

### 1. Install SAM CLI

[AWS SAM CLI Installation Guide](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/install-sam-cli.html)

### 2. Build

``` bash
sam build -t master.yaml
```

### 3. Deploy

``` bash
sam deploy --stack-name AWS-Sensei-Blog-CICD --resolve-s3 --capabilities CAPABILITY_NAMED_IAM
```

------------------------------------------------------------------------

## 📚 What Each Template Does

### **master.yaml**

The orchestration file.\
Includes all nested yaml files.

### **roles.yaml**

IAM roles for

- CodePipeline
- CodeBuild
- CloudFormation

### **artifacts.yaml**

Creates buckets for

- CodePipeline artifacts

### **codebuild.yaml**

CodeBuild project for

- Hugo build

### **pipeline.yaml**

Defines pipeline

1. GitHub source
2. InfraDeploy via SAM/CloudFormation
3. Hugo build + deploy

------------------------------------------------------------------------

## 🔑 Secrets

GitHub token for CodePipeline source action is stored in Secrets Manager.

------------------------------------------------------------------------
