 ## Ansible first steps:

* Requirement for ansible control machine:
**Python 2** (versions 2.6 or 2.7) or **Python 3** (versions 3.5 and higher) installed (**Windows isn’t supported** for the control machine)

* Ansible installation:
https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html

* Checking path to config file:
ansible --version

* Before start work uncomment in **ansible.cfg**:
host_key_checking=False
log_path=/appserver/ansible/logs/ansible.log

* To add hosts to inventory - file hosts could be used. Save default file under hosts.old. After that you could add hosts to newly created emty hosts file.:
mv hosts hosts.old && touch hosts
