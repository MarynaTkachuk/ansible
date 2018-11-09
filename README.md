 ## Ansible first steps:

* Requirement for ansible control machine:
**Python 2** (versions 2.6 or 2.7) or **Python 3** (versions 3.5 and higher) installed (**Windows isn’t supported** for the control machine)

* Ansible installation:
https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html

* Checking path to config file:
```
ansible --version
```

* Before start work uncomment in **ansible.cfg**:
```
host_key_checking=False
log_path=/appserver/ansible/logs/ansible.log
```

* To add hosts to inventory - file hosts could be used. Save default file under hosts.old. After that you could add hosts to newly created emty hosts file:
```
mv hosts hosts.old && touch hosts
```
* After adding hosts to hosts file. Connection could be checked with ansinle ping. User - user used for servers, assuming that all servers had the same `user` user. After that password for this user will be required (assume that all users have the same password):
```
 ansible all -m ping -u user -k
 ```

* To set up passwordless autorization beetween control host and controlled hosts:
1. On control machine (under user, which would run playbooks) generate ssh-key with command:
```
ssh-keygen
```
2. After that playbook **authorized_key.ym** could be used for setting up passwordless autorization with command:
```
ansible-playbook authorized_key.yml -e user=someuser -k
```
After correct SSH password input and successful run of playbook next run of any playbook for inventory hosts will be without password (-k option). 


 ## Some usefull commands
 See all available modules:
 ```
 ansible-doc -l
 ```
## Theory
For each task Ansible does: 
1) establishes ssh session
2) creates temp folder on remote system 
3) copies “shell” module file to remote system 
4) executes python shell.py on remote host 
5) removes all files it created before 
6) terminates connection 
7) ansible processes task’s output and prints it to stdout

You can see this with maximum verbosity mode: -vvv
