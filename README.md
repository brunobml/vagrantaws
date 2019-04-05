# Vagrant AWS Repo

## Table of Contents

* [Deployment Tools](#deployment-tools)
* [Vagrant Usage](#vagrant-usage)
  * [Vagrant Documentation](#vagrant-documentation)
* [Set AWS Credentials](#Set-AWS-Credentials)
* [Prerequisites](#Preresquisites)

## Deployment Tools

* Vagrant - minimum v2.2.4

    To verify version: vagrant -v

## Vagrant Usage

Vagrant is used to provide a common deployment platform. It is also possible to use `Windows Sub-system for Linux` or another container/virtualization technology. The Vagrantfile provided in this repository leverages the vagrant-aws provider, this will create a vagrant ec2 instance in AWS. The vagrant image will provides all of the deployment tools necessary to create a packer ami and deploy the cloud environment using terraform, in addition to the most up-to-date awscli to troubleshoot or administer AWS via cli if needed.

* [How to use this Vagrantfile](https://bitbucket.org/cenovus/vagrantfile-templates/src/master/README.md)
  * See the Vagrant-AWS Provider section

## Set AWS Credentials

* Preferred: IAM Role or AWS Temporary Credentials, below is an example of setting environment variables with AWS Temporary Credentials

        export AWS_ACCESS_KEY_ID="######################"
        export AWS_SECRET_ACCESS_KEY="######################"
        export AWS_SESSION_TOKEN="######################"

* Configure AWS 
%userprofile%/.aws/credentials

```bash
[default]
aws_access_key_id = <PASTE KEY ID>
aws_secret_access_key = <PASTE SECRET ACCESS KEY>
```
#Preresquisites

make sure aws cli installed

Install the following vagrant plugins

```bash
 vagrant plugin install --plugin-version 1.0.1 fog-ovirt
 vagrant plugin install vagrant-aws
 vagrant box add aws-dummy https://github.com/mitchellh/vagrant-aws/raw/master/dummy.box
 vagrant up
 ```

