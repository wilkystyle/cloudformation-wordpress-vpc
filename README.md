# Cloudformation WordPress VPN

Ansible playbook/role to run a Cloudformation template that creates a VPC with sample WordPress site.

## Requirements

To execute the configuration in this repository, you must ensure that the following dependencies are installed on your machine:

* Ansible ([Yum](http://docs.ansible.com/ansible/intro_installation.html#latest-release-via-yum)/[Apt](http://docs.ansible.com/ansible/intro_installation.html#latest-releases-via-apt-ubuntu)/[OSX](http://docs.ansible.com/ansible/intro_installation.html#latest-releases-on-mac-osx))
* Python >= 2.6
* [boto](http://boto.cloudhackers.com/en/latest/getting_started.html)

## Creating the stack

First, make sure that you have exported your AWS credentials:

    $ export AWS_ACCESS_KEY_ID="[YOUR ACCESS KEY]"
    $ export AWS_SECRET_ACCESS_KEY="[YOUR SECRET ACCESS KEY]"

Next, run the Ansible playbook to create the stack and the local `wordpress` inventory file:

    $ ansible-playbook create.yml -i aws

You will be prompted for the EC2 key pair ID that you wish to use for access to the EC2 instance after it is created. This must be the ID of the keypair you will use in the command below.

Finally, run the Ansible playbook to provision the WordPress site, supplying the key file for EC2 access:

    $ ansible-playbook provision.yml -i wordpress --private-key=/path/to/ec2/key.pem
