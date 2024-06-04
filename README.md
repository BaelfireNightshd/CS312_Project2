# Minecraft Server on AWS with Pulumi and Ansible

## Installing Pulumi
To install Pulumi, go to the [website](https://www.pulumi.com/docs/install/) and get the latest command to run to install. 

```bash
curl -fsSL https://get.pulumi.com | sh
```

You should now be able to verify that it works by running
```bash
pulumi version
```

## Making the Pulumi Project
To make a new AWS project in Pulumi that will use YAML as the configuration language, run the following command. Note that the folder needs to be empty. 
```bash
pulumi new aws-yaml
```

Answer the questions it asks you. Example:
```
This command will walk you through creating a new Pulumi project.

Enter a value or leave blank to accept the (default), and press <ENTER>.
Press ^C at any time to quit.

project name (project): CS312_Project2
project description (A minimal AWS Pulumi YAML program): Minecraft on AWS with Ansible and Pulumi
Created project 'CS312_Project2'

Please enter your desired stack name.
To create a stack in an organization, use the format <org-name>/<stack-name> (e.g. `acmecorp/dev`).
stack name (dev): dev
Created stack 'dev'

aws:region: The AWS region to deploy into (us-east-1):
Saved config

Your new project is ready to go!

To perform an initial deployment, run `pulumi up`
```

