[Virtual Machine](VM.md) | [Ansible](Ansible.md) | [Playbooks](Playbooks.md)

## Creating Virtual Machine

* Install [vagrant](https://www.vagrantup.com/downloads.html).
* Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads) is a recommended provider.
  Other [virtual machine providers](https://docs.vagrantup.com/v2/providers/) do exist. 

Initialize a virtual machine. `ubuntu/trusty64` is one default image. A list of other virtual machine images can be found [here](https://atlas.hashicorp.com/boxes/search).

    vagrant init ubuntu/trusty64

Start up the virtual machine.

    vagrant up

Then    

    vagrant ssh

You should be able to connect to the machine.

#### Windows help

* If you're running Hyper-V and VirtualBox, and you're experiencing crashes when you try to start a VM, you may need to turn off Hyper-V (which exclusively locks use of CPU for virtualization).
* If you can't run vagrant ssh, Add `C:\Program Files\Git\usr\bin` to your PATH, which includes `ssh`.

## SSH Keys

## Vagrantfile

## Virtualbox Networking

