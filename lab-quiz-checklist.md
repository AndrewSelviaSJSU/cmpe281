# Lab Quiz Prep

## Basic Prep
* Setup
    * Spin up your jumpbox, php-instance, docker-container (EC2-Instances)
    * Check that the routing table for your **private subnets** have a NAT gateway
    * Check that the routing table for your **public subnets**  have an Internet gateway
    * Start up NAT gateway and associate it with the routing table (for your private subnets)
    * Make separate folders for your screenshots/generated pdfs
    * Double check .png to .pdf is working

* Sanity Check
    * SSH/SCP
        * SSH into jumpbox
        * SSH into public instances
        * SSH from jumpbox to private instances
    * Routing
        * Check NAT gateway is working in private instances (sudo yum update while inside private instance)
        * Check Internet gateway is working in public stances (ping the instance)
    * Scripting
        * Make scripts to access resources quickly (sample below)

## Scripting
```
ssh -i key-pair.pem ec2-user@$1
ssh -i key-pair.pem centos@$1
scp -i key-pair.pem $1 ec2-user@$2:/home/ec2-user/
scp -i key-pair.pem $1 centos@$2:/home/centos/
etc...
``` 
