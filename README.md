# IT Vedant DevOps Assessment

## Overview

This project demonstrates a complete DevOps workflow using AWS, GitHub Actions, Docker, Amazon ECR, Amazon EKS, S3, CloudFront, Application Load Balancer, and Auto Scaling.

## Architecture

```text
Developer
   |
   v
GitHub Repository
   |
   v
GitHub Actions
   |
   +--> Run Tests
   |
   +--> Build Docker Image
   |
   +--> Push Image to Amazon ECR
   |
   v
Amazon EKS
   |
   v
Kubernetes Service
   |
   v
Application


Static Content:

S3 Bucket
   |
   | Private access through OAC
   v
CloudFront
   |
   v
Users


EC2 Scaling:

Internet
   |
   v
Application Load Balancer
   |
   v
Target Group
   |
   +--> EC2 Instance
   |
   +--> EC2 Instance
          |
          v
     Auto Scaling Group
          |
          +--> CPU Target: 70%
          +--> Min: 2
          +--> Desired: 2
          +--> Max: 4


