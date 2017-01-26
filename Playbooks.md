[Virtual Machine](VM.md) | [Ansible](Ansible.md) | [Playbooks](Playbooks.md)

### Commands/Modules

In examples folder, execute the [commands.yml](examples/commands.yml) playbook.

```bash
ansible-playbook commands.yml
```

This will ensure a .ssh directory exists and creates a ssh key. Inspect the directory and ensure it exists. 

* Run the command again. You should see changes=0.
* Manually delete the ssk key that was generated. Run the command again.

### Variables/Loops

In examples folder, execute the [loops.yml](examples/loops.yml) playbook.
This will install git and print out a list of packages. Instead of running on your localhost, this will run on all servers in the `[nodes]` group. The `-s` option will allow the playbook to sudo as root if necessary.

```bash
ansible-playbook -i inventory loops.yml -s
```

Extend the example to run now install all packages defined in the packages variable.

### Output/Register/Conditions

### Templates

### Roles
