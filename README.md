# Ansible Playbook for GitLab

This is a playbook for deploy automatically a gitlab solution on Ubuntu

## Install
For run playbook, run the command below. The password for vault is rootroot
```bash
ansible-playbook main.yml -i inventory.yml --ask-vault-pass
```

### Roles
There is two roles available. The first, apache, install apache2 for serve gitlab outside.<br>
The seconde role is gitlab for the install and configuration of gitlab.

### Variables
The apache role has one variable<br>
|Name|Description|Default value|
|:---|:----------|:------------|
gitlab_site|Public address for gitlab instance|gitlab.student.local

The gitlab role has some variables
|Name|Description|Default value|
|:---|:----------|:------------|
gitlab_address|Local address for gitlab instance|localhost
gitlab_port|Local port for gitlab instance|8888
gitlab_https|Enable https for gitlab instance|false
gitlab_external|External address for gitlab instance. Based on apache configuration|http://gitlab.student.local

The default user/password for GitLab is set on roles/gitlab/vars/secure.yml vault.

## Open
When the playbook is done, go to http://gitlab.student.local/<br>
The default gitlab user is root with password rootroot
