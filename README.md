# Minecraft Server on AWS with Pulumi and Ansible

## Prerequisites
### Installing Pulumi
To install Pulumi, go to the [website](https://www.pulumi.com/docs/install/) and get the latest command to run to install. 

```bash
curl -fsSL https://get.pulumi.com | sh
```

You should now be able to verify that it works by running
```bash
pulumi version
```

### AWS Credentials
Copy your AWS credentials into the file `~/.aws/credentials`.

### Clone Project
```bash
git clone git@github.com:BaelfireNightshd/CS312_Project2.git
cd CS312_Project2/pulumi
```

### Set up private keys
```bash
ssh-keygen -t ed25519 -f .pulumi_awsacad
pulumi config set publicKeyPath .pulumi_awsacad.pub
pulumi config set privateKeyPath .pulumi_awsacad
```

## Bringing up
```bash
pulumi up
```

## Bringing down
```bash
pulumi down
```

## Connecting
### nmap

### Minecraft




## References
1. https://www.pulumi.com/docs/clouds/aws/get-started/
1. https://www.pulumi.com/registry/packages/aws/api-docs/ec2/instance/
1. https://www.pulumi.com/blog/deploy-wordpress-aws-pulumi-ansible/
