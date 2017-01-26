[Virtual Machine](VM.md) | [Ansible](Ansible.md) | [Playbooks](Playbooks.md)

### Commands/Modules

In examples folder, execute the [commands.yml](examples/commands.yml) playbook.

```bash
ansible-playbook commands.yml
```

This will ensure a .ssh directory exists and creates a ssh key. Inspect the directory and ensure it exists. Notice that this runs on your ansible server and not your nodes. That's because the hosts in the playbook is specified as localhost.

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

When a module is executed, you can save the results of that command using `register`.
Further, you can use conditions to control whether a task is executed with `when`.
You can control whether a command is considered changed, using `changed_when`.

For example, this command will save the output of `echo` into the variable `out`.
Its changed status will change depending on whether there is a list item with z.

```yaml
- action: command echo {{item}}
  register: out
  changed_when: "'z' in out.stdout"
  with_items:
    - hello
    - foo
    - bye
```

Mixing `register`, `changed_when`, and `with_items` can get tricky. Based on context, sometimes the variable saved in register will change per item during task execution. Othertimes, when all done contain a list of all items and their results. For some more details:
[see this example](http://stackoverflow.com/a/41292571/547112).

Ok. Check out [results.yml](examples/results.yml). There is a task that downloads a file. But since it uses the `shell` command it doesn't know that the task has already been done. It isn't idempotent and it will wastefully download the file over and over again!

Change the command so that there is a task that first checks if 



### Templates

### Vaults

You can 

### Roles
