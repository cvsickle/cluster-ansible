# cluster-ansible
Ansible setup for cluster provisioning

# Variable setup

Create a variable file from the sample:

```bash
cp ./inventory/group_vars/all.yml.sample ./inventory/group_vars/all.yml
```

Edit the variables to match the setup. Note, Bitwarden secrets can be used. See the commented out portions of the sample variables file. See [ansible-integration/](https://bitwarden.com/help/ansible-integration/) for more information.

# Example Commands

> [!NOTE]
> The `--user` argument specifies the user to run commands as on the remote hosts.

### Ping host `test` from `test.yml` inventory

```bash
ansible -i ./inventory/test.yml test -m ping
```

### Run the `apt.yml` playbook on `test.yml` inventory

> [!NOTE]
> The `--ask-become-pass` argument will prompt for the `sudo` password of the remote hosts.

```bash
ansible-playbook ./playbooks/apt.yml -i ./inventory/test.yml
```

### Run all the playbooks in `run.yml` on the `test.yml` inventory

```bash
ansible-playbook run.yml -i ./inventory/test.yml
```

# Helpful References
- [https://technotim.live/posts/ansible-automation/](https://technotim.live/posts/ansible-automation/)
- [https://github.com/timothystewart6/launchpad](https://github.com/timothystewart6/launchpad)
- [https://github.com/timothystewart6/k3s-ansible](https://github.com/timothystewart6/k3s-ansible)
