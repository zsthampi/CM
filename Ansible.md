[Virtual Machine](VM.md) | [Ansible](Ansible.md) | [Playbooks](Playbooks.md)

Ansible is a tool for configuring and coordinating software on multiple machines.
In general, Ansible (like Salt, Chef, and Puppet), use a central server that controls other nodes.  Unlike the other tools, Ansible does not require a client service to run on the nodes.

![image](https://cloud.githubusercontent.com/assets/742934/22233647/b26951a4-e1bf-11e6-9bff-0a168a8dc66b.png)

## Setting up Ansible

Follow these steps to install Ansible on your configuration server.

```bash
sudo apt-get update
# Basic dev deps
sudo apt-get -y install git make vim python-dev python-pip libffi-dev libssl-dev libxml2-dev libxslt1-dev libjpeg8-dev zlib1g-dev
# Ansible, setuptools, dopy
pip install ansible==2.2.0
pip install -U pip setuptools>=11.3
pip install dopy==0.3.5
```
