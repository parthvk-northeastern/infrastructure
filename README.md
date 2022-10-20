# AWS CloudFormation

AWS CLI: https://docs.aws.amazon.com/cli/latest/reference/cloudformation/index.html


aws cloudformation create-stack --stack-name myvpc --template-body file://1_vpc.yaml


aws cloudformation create-stack --stack-name myvpcwithparam --template-body file://vpc.yml --parameters ParameterKey=VpcCidrBlock,ParameterValue="10.1.1.0/24"


aws cloudformation update-stack --stack-name myvpc --template-body file://vpc.yml

## AWS Profile

aws configure --profile devparth

aws configure --profile=dev

aws configure --profile=prod

export AWS_PROFILE=dev

export AWS_PROFILE=prod

## AWS Networking

aws ec2 create-vpc --cidr-block "10.0.0.0/16" --no-amazon-provided-ipv6-cidr-block --instance-tenancy default

aws ec2 delete-vpc --vpc-id vpc-08ccb95c7042bc32e

aws ec2 delete-stack --stack-name myvpc

aws ec2 describe-vpcs --filters Name=Name,Values=demo

aws ec2 modify-vpc-attribute --enable-dns-hostnames --enable-dns-support --vpc-id <value>

aws ec2 modify-vpc-attribute --no-enable-dns-hostnames --vpc-id vpc-08f37ad6c277af8a5


## AWS CLI

export AWS_PROFILE=dev

export AWS_REGION=us-east-1

aws cloudformation create-stack --stack-name myvpc --template-body file://vpc.yaml --parameters ParameterKey=az1,ParameterValue=0 ParameterKey=az2,ParameterValue=1  ParameterKey=az3,ParameterValue=2

aws cloudformation create-stack --stack-name myvpc1 --template-body file://csye6225-infra.yml --parameters ParameterKey=az1,ParameterValue=0 ParameterKey=az2,ParameterValue=1  ParameterKey=az3,ParameterValue=2 ParameterKey=KeyName,ParameterValue=aws ParameterKey=LatestAmiId,ParameterValue=ami-06ca5b163c5aec5d9 --region us-east-1 --profile demoparth 

aws cloudformation create-stack --stack-name myvpc1 --template-body file://vpc.yaml --parameters ParameterKey=az1,ParameterValue=0 ParameterKey=az2,ParameterValue=1  ParameterKey=az3,ParameterValue=1 --region us-west-1 --profile dev

aws cloudformation delete-stack --stack-name myvpc1 --region us-east-1 --profile devparth


