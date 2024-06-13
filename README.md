# Minecraft Server on AWS with Pulumi and Ansible

## Background
![Flow chart of process](Flow_Diagram.drawio.svg)
We will provision the resources in AWS using Pulumi. Then, using Ansible, installs a Minecraft server and sets up a systemd service to start it on reboot. 

## Prerequisites
You need to have an OSU IP address to have SSH access without editing the Security Group definition. 

### Installing Pulumi
To install Pulumi, go to the [website](https://www.pulumi.com/docs/install/) and get the latest command to run to install. 

```bash
curl -fsSL https://get.pulumi.com | sh
```

You should now be able to verify that it works by running
```bash
pulumi version
```

### Installing Ansible
To install Ansible, go to the [website](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) and get the latest command to install. 
```bash
sudo apt install pipx
pipx install --include-deps ansible
pipx ensurepath
```

### AWS Credentials
Copy your AWS credentials into the file `~/.aws/credentials` to be able to provision resources on AWS with Pulumi. 

### Clone Project
Cloning the project and initializing a new stack with Pulumi. 
```bash
git clone https://github.com/BaelfireNightshd/CS312_Project2.git
cd CS312_Project2/pulumi
pulumi stack init
```

### Set up private keys
Private keys to manage the machine with Pulumi/Ansible over SSH then telling Pulumi where to find the keys. 
```bash
ssh-keygen -t ed25519 -f .pulumi_awsacad
pulumi config set publicKeyPath .pulumi_awsacad.pub
pulumi config set privateKeyPath .pulumi_awsacad
```

## Bringing up
Here is the command to actually set up the minecraft server in AWS with Pulumi. 
```bash
pulumi up
```

## Bringing down
Here is the command to take the server down if needed. 
```bash
pulumi down
```

## Connecting
### nmap
To test with NMAP, run the following command.
```bash
nmap -sV -Pn -p T:25565 <instance_public_ip>
```

### Minecraft
Enter the public IP address when connecting to a server in Java Minecraft. 



## References
1. https://www.pulumi.com/docs/clouds/aws/get-started/
1. https://www.pulumi.com/blog/deploy-wordpress-aws-pulumi-ansible/
1. Various Pulumi documentation pages.
1. https://stackoverflow.com/questions/26638180/write-variable-to-a-file-in-ansible
1. https://www.pulumi.com/docs/concepts/options/dependson/
1. https://www.baeldung.com/linux/systemd-unit-file-permissions
