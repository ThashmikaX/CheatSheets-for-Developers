---
title: Ansible CheatSheet
description: The most commonly used Ansible commands are given here.
created: 2026-01-27
---

## Table of Contents

- [Ansible CheatSheet for Developers](#ansible-cheatsheet-for-developers)
  - [Check Ansible Setup and Configuration](#check-ansible-setup-and-configuration)
  - [Inventory and Connectivity](#inventory-and-connectivity)
  - [Running Ad-hoc Commands](#running-ad-hoc-commands)
  - [Playbooks](#playbooks)
  - [Roles](#roles)
  - [Variables and Facts](#variables-and-facts)
  - [Ansible Galaxy](#ansible-galaxy)
  - [Ansible Vault](#ansible-vault)
  - [Miscellaneous Commands](#miscellaneous-commands)

# Ansible CheatSheet for Developers

## Check Ansible Setup and Configuration

| Command                         | Description                                              |
| :-----------------------------: | -------------------------------------------------------- |
| `ansible --version`             | Display Ansible version and configuration paths          |
| `ansible-config list`           | List all Ansible configuration options                   |
| `ansible-config view`           | View the active Ansible configuration                    |
| `ansible-doc -l`                | List all available Ansible modules                       |

**[🔼Back to Top](#table-of-contents)**

## Inventory and Connectivity

| Command                                               | Description                                               |
| :---------------------------------------------------: | --------------------------------------------------------- |
| `ansible all -i inventory -m ping`                    | Test connectivity to all hosts                            |
| `ansible all -m ping`                                 | Ping all hosts using default inventory                    |
| `ansible web -i inventory -m ping`                    | Ping hosts in the `web` group                             |
| `ansible-inventory --list -y`                         | Display inventory in YAML format                          |
| `ansible-inventory --graph`                           | Display inventory as a graph                              |

**[🔼Back to Top](#table-of-contents)**

## Running Ad-hoc Commands

| Command                                                             | Description                                              |
| :-----------------------------------------------------------------: | -------------------------------------------------------- |
| `ansible all -m shell -a "uptime"`                                   | Run shell command on all hosts                           |
| `ansible web -m command -a "df -h"`                                  | Run command module on `web` hosts                        |
| `ansible all -m copy -a "src=a.txt dest=/tmp/a.txt"`                | Copy file to remote hosts                                |
| `ansible all -m yum -a "name=httpd state=present" -b`               | Install package using privilege escalation               |
| `ansible all -m service -a "name=httpd state=started" -b`           | Start a service                                          |

**[🔼Back to Top](#table-of-contents)**

## Playbooks

| Command                                         | Description                                               |
| :---------------------------------------------: | --------------------------------------------------------- |
| `ansible-playbook site.yml`                     | Run a playbook                                           |
| `ansible-playbook site.yml -i inventory`        | Run playbook with specific inventory                     |
| `ansible-playbook site.yml --check`             | Dry run (check mode)                                     |
| `ansible-playbook site.yml --diff`              | Show differences when files change                       |
| `ansible-playbook site.yml -l web`              | Limit execution to `web` hosts                            |
| `ansible-playbook site.yml -t install`          | Run tasks with specific tag                               |
| `ansible-playbook site.yml --start-at-task "X"` | Start execution from a specific task                     |

**[🔼Back to Top](#table-of-contents)**

## Roles

| Command                                   | Description                                         |
| :---------------------------------------: | --------------------------------------------------- |
| `ansible-galaxy init my_role`             | Create a new role structure                         |
| `ansible-galaxy list`                     | List installed roles                                |
| `ansible-galaxy install nginxinc.nginx`   | Install role from Ansible Galaxy                   |
| `ansible-galaxy remove nginxinc.nginx`    | Remove an installed role                            |

**[🔼Back to Top](#table-of-contents)**

## Variables and Facts

| Command                                               | Description                                               |
| :---------------------------------------------------: | --------------------------------------------------------- |
| `ansible all -m setup`                                | Gather facts from all hosts                               |
| `ansible all -m setup -a "filter=ansible_os_family"`  | Filter specific facts                                     |
| `ansible-playbook site.yml -e "env=prod"`             | Pass extra variables via CLI                              |
| `ansible-playbook site.yml -e @vars.yml`              | Load variables from a file                                |

**[🔼Back to Top](#table-of-contents)**

## Ansible Galaxy

| Command                                       | Description                                           |
| :-------------------------------------------: | ----------------------------------------------------- |
| `ansible-galaxy search mysql`                 | Search roles on Ansible Galaxy                        |
| `ansible-galaxy install geerlingguy.mysql`    | Install role from Galaxy                              |
| `ansible-galaxy collection list`              | List installed collections                            |
| `ansible-galaxy collection install community.aws` | Install a collection                             |

**[🔼Back to Top](#table-of-contents)**

## Ansible Vault

| Command                                      | Description                                           |
| :------------------------------------------: | ----------------------------------------------------- |
| `ansible-vault create secrets.yml`           | Create an encrypted file                              |
| `ansible-vault edit secrets.yml`             | Edit an encrypted file                                |
| `ansible-vault encrypt vars.yml`              | Encrypt an existing file                              |
| `ansible-vault decrypt vars.yml`              | Decrypt a file                                        |
| `ansible-playbook site.yml --ask-vault-pass` | Run playbook with vault password prompt               |

**[🔼Back to Top](#table-of-contents)**

## Miscellaneous Commands

| Command                                   | Description                                             |
| :---------------------------------------: | ------------------------------------------------------- |
| `ansible-doc yum`                         | Show documentation for a module                         |
| `ansible-playbook site.yml -vvv`          | Run playbook with verbose output                        |
| `ansible localhost -m debug -a "var=hostvars"` | Debug variables                                   |

**[🔼Back to Top](#table-of-contents)**
