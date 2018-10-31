## Ansible first steps:

* Requirement for ansible control machine:
**Python 2** (versions 2.6 or 2.7) or **Python 3** (versions 3.5 and higher) installed (**Windows isn’t supported** for the control machine)

* Ansible installation:
pip install ansible[==2.7.1]

## General playbooks description:

**authorized_key.yml** - check and add authorized key (.pub key for current user, who run playbook) for remote servers to enable paswordless comunication beetween ansible control host and controlled hosts.

**create_user.yml** - playbook for creating a user on remote system with defined variables;

**disable_puppet.yml** - for disabling puppet agent on remote system, and do checks - that it disabled;

**disable_service.yml** - for disabling some service and than make sure it`s not running;
