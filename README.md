# cluster-ansible
Ansible setup for cluster provisioning

# Example Commands

Ping host `test` from `test.yml` inventory:
```bash
ansible -i ./inventory/test.yml test -m ping --user corey
```

Run the `apt.yml` playbook on `test.yml` inventory:

> [!NOTE]
> The `--ask-become-pass` argument will prompt for the `sudo` password of the remote host.

```bash
ansible-playbook ./playbooks/apt.yml --user corey --ask-become-pass -i ./inventory/test.yml
```
