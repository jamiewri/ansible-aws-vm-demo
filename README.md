# ansible-aws-vm-demo

This is an example playbook designed to deploy webservers and loadbalancers in a HA vm-based architecture on AWS.

If you are looking for a modular, idempotent example of provisioning infrastructure and then configuring it to serve a simple use case (i.e. learning Ansible) then this repo should serve as a good starting point.

In short it deploys a VPC, IGW, Default Route, Subnets and Security Groups. Then configures a definable number of VM based httpd servers with a definable number of VM based loadbalancers in front of them. 

Tested with up to 2 loadbalancers and 3 webservers.

SELinux ENABLED

## Requirements
- Boto
- Ansible
- AWS account (this can all run on the free tier)
- AWS SSH key-pair located at “~/Desktop/key-pair-example.pem”

## Configurables
- main.yml
- host_vars/locahost.yml

## Caveats 
Designed to be deployed from outside of your VPC, with security groups setup to restrict access to your public IP. This would not be considered a best practice but makes it easy to get started without having to proxy Ansible through a jumphost.

