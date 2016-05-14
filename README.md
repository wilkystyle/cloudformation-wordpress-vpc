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

Then, run the Ansible playbook to create the stack:

    $ ansible-playbook create.yml -i aws
