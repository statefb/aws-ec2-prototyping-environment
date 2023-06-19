# AWS EC2 Prototyping Environment

## Overview

This repository is designed to help you quickly start prototyping with AWS. It sets up an EC2 instance, configured to be accessed via Remote SSH such as [VSCode](https://code.visualstudio.com/docs/remote/ssh). The only requirement is an AWS account.

### What's included

This setup comes pre-installed with Python, Node.js, and Docker, which are commonly used for development in AWS.

## Instructions

- Open [CloudShell](https://console.aws.amazon.com/cloudshell/home) in AWS.
- Clone this repository.

```
git clone https://github.com/statefb/aws-ec2-prototyping-environment
```

- Run the script. The first argument should be the access source IP's CIDR, the second argument is the stack name. **Substitute `XX.XX.XX.XX` to your environment accordingly.**

```
cd aws-ec2-prototyping-environment
```

```
./bin.sh XX.XX.XX.XX/32 MyProtoStack
```

- Copy ssh key displayed on CloudShell to your clipboard, then save it locally as `prototype.pem`.
- Change the permission of the pem file.

```
chmod 400 prototype.pem
```

- Login using SSH command. The IP address can be found at the bottom of output on CloudShell as `HostPublicIP`.

```
ssh -i prototype.pem ec2-user@XX.XX.XX.XX
```

## Note

The third and fourth argument to the ./bin.sh command can specify the instance size and volume size respectively.  
By default, these are `t2.large` and `128GB`.
