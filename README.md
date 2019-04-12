# Vagrant AWS Repo

## Table of Contents

* [Deployment Tools](#deployment-tools)
* [Vagrant Usage](#vagrant-usage)
* [Set AWS Credentials](#Set-AWS-Credentials)
* [Prerequisites](#Preresquisites)
* [All Vagrant commands](#All-Vagrant-commands)

## Deployment Tools

* Vagrant - minimum v2.2.4

    To verify version: vagrant -v

## Vagrant Usage

Vagrant is used to provide a common deployment platform. It is also possible to use `Windows Sub-system for Linux` or another container/virtualization technology. The Vagrantfile provided in this repository leverages the vagrant-aws provider, this will create a vagrant ec2 instance in AWS. The vagrant image will provides all of the deployment tools necessary to create a packer ami and deploy the cloud environment using terraform, in addition to the most up-to-date awscli to troubleshoot or administer AWS via cli if needed.

## Set AWS Credentials

* Preferred: IAM Role or AWS Temporary Credentials, below is an example of setting environment variables with AWS Temporary Credentials

        export AWS_ACCESS_KEY_ID="######################"
        export AWS_SECRET_ACCESS_KEY="######################"
        export AWS_SESSION_TOKEN="######################"

* Configure AWS credentials
       
        If there are no credentials declared on the Vagrantfile, the credentials will use the default location on the :
        %userprofile%/.aws/credentials


```bash
[default]
aws_access_key_id = <PASTE KEY ID>
aws_secret_access_key = <PASTE SECRET ACCESS KEY>
```
## Preresquisites

make sure aws cli installed

Install the following vagrant plugins

```bash
 vagrant plugin install --plugin-version 1.0.1 fog-ovirt
 or
 vagrant plugin install --plugin-version 1.0.1 fog-ovirt --plugin-source http://rubygems.org
 vagrant plugin install vagrant-aws
 vagrant box add aws-dummy https://github.com/mitchellh/vagrant-aws/raw/master/dummy.box
 vagrant up
 ```

## All Vagrant commands

    List Vagrant commands:

```bash
vagrant
Example:

Usage: vagrant [options] command> [args>]
 
 -v, --version                    Print the version and exit.
 -h, --help                       Print this help.
 
Common commands:
  box             manages boxes: installation, removal, etc.
  connect         connect to a remotely shared Vagrant environment
  destroy         stops and deletes all traces of the vagrant machine
  global-status   outputs status Vagrant environments for this user
  halt            stops the vagrant machine
  help            shows the help for a subcommand
  init            initializes a new Vagrant environment by creating a Vagrantfile
  login           log in to HashiCorp's Vagrant Cloud
  package         packages a running vagrant environment into a box
  plugin          manages plugins: install, uninstall, update, etc.
  port            displays information about guest port mappings
  powershell      connects to machine via powershell remoting
  provision       provisions the vagrant machine
  push            deploys code in this environment to a configured destination
  rdp             connects to machine via RDP
  reload          restarts vagrant machine, loads new Vagrantfile configuration
  resume          resume a suspended vagrant machine
  share           share your Vagrant environment with anyone in the world
  snapshot        manages snapshots: saving, restoring, etc.
  ssh             connects to machine via SSH
  ssh-config      outputs OpenSSH valid configuration to connect to the machine
  status          outputs status of the vagrant machine
  suspend         suspends the machine
  up              starts and provisions the vagrant environment
  validate        validates the Vagrantfile
  version         prints current and latest Vagrant version
```


For help on any individual command run `vagrant COMMAND -h`
 
Additional subcommands are available, but are either more advanced
or not commonly used. To see all subcommands, run the command

```bash
vagrant list-commands
```
