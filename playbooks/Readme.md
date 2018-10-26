## General playbooks description:

**authorized_key.yml** - check and add authorized key (.pub key for current user, who run playbook) for remote servers to enable paswordless comunication beetween ansible control host and controlled hosts.

**create_user.yml** - playbook for creating a user on remote system with defined variables;

**disable_puppet.yml** - for disabling puppet agent on remote system, and do checks - that it disabled;

**disable_service.yml** - for disabling some service and than make sure it`s not running;
