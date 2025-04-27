# Ansible Learning Notes

Welcome to my Ansible learning notes repository! This repo contains my personal notes, examples, and best practices as I learn and work with Ansible. The content here covers a variety of topics, ranging from basic concepts to more advanced techniques.

## Table of Contents

- [Introduction to Ansible](#introduction-to-ansible)
- [Installation](#installation)
- [Basic Usage](#basic-usage)
- [Playbooks](#playbooks)
- [Ansible Vault](#ansible-vault)
- [Roles](#roles)
- [Modules](#modules)
- [Examples](#examples)
- [Best Practices](#best-practices)

## Introduction to Ansible

Ansible is an open-source automation tool used to configure systems, deploy applications, and orchestrate tasks. It is agentless, meaning it doesn't require any special software to be installed on the target machines, only SSH access.

In this repository, I will be documenting various aspects of Ansible as I work through learning resources and hands-on labs.

## Installation

To get started with Ansible, you can install it using the following methods:

### On Ubuntu
```bash
sudo apt update
sudo apt install ansible
```
For other operating systems, please refer to the official installation guide.

## Basic Usage
Ansible is typically used with the command-line tool, ansible, for executing commands or ansible-playbook for running playbooks.

Here’s an example of running a simple command on remote servers:
```
ansible all -m ping -u your_user
```

## Playbooks
Playbooks are YAML files that describe a set of tasks to be executed on remote systems. Here's a basic example:
```yaml
- name: Install Apache Web Server
  hosts: webservers
  become: yes

  tasks:
    - name: Install apache2
      apt:
        name: apache2
        state: present
```

## Ansible Vault
Ansible Vault allows you to keep sensitive data (like passwords or keys) encrypted in your playbooks. To create an encrypted file:
```
ansible-vault create secret.yml
```

## Roles
Roles are a way of organizing Ansible playbooks and files into reusable components. Here’s how to create a role:
```bash
ansible-galaxy init my_role
```
This command will generate a role structure with directories for tasks, handlers, and more.

## Modules
Ansible modules are small pieces of code that do the work within a playbook. Here’s an example of using the apt module to install a package:

```yaml
- name: Install a package
  apt:
    name: vim
    state: present
```
## Examples
This section contains various examples of real-world Ansible usage, such as provisioning servers, managing configurations, and deploying applications.

## Best Practices
In this section, I’ll share some best practices for using Ansible effectively, such as:
- Using roles for modularity
- Keeping playbooks idempotent
- Structuring directories and files clearly

Feel free to browse through the repository to see examples, notes, and tips. As I continue learning, I’ll add more content to help me (and you) understand Ansible better.

Happy Automating!
