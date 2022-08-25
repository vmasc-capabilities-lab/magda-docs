# AWS

## Creating a cluster 

To create a EKS cluster on AWS, you can find out how [here ](https://docs.aws.amazon.com/eks/latest/userguide/getting-started-eksctl.html).

We chose to deploy with managed linux nodes instead of Fargate as there were initial issues with deployment on Fargate managed nodes.

Create AWS EKS Cluster command : 

`eksctl --profile {AWS-Profile-NAME} create cluster --name {Cluster-NAME} --region {Cluster-AWS-Region}`


## Connecting to AWS Cluster

To develop and push updates to VCL version of Magda you will need to connect to the AWS hosted cluster. You will need to have the necessary permissions in order to connect. 

1. Follow [these instructions](https://aws.amazon.com/premiumsupport/knowledge-center/eks-cluster-connection/) for connecting your kubectl cli to the AWS hosted cluster.

   - Region: us-east-2
   - Cluster name: magda-config-cluster