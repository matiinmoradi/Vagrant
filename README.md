# Vagrant
Vagrant + Ansible + Nginx Lab

A simple Infrastructure as Code (IaC) lab built with **Vagrant** and **Ansible**.

This project provisions multiple Ubuntu virtual machines using Vagrant and automatically installs and configures Nginx on the web servers with Ansible.

## Architecture

```
                +----------------+
                |    Control VM  |
                |    Ansible     |
                +--------+-------+
                         |
            -----------------------------
            |                           |
     +------+-------+           +-------+------+
     |    Web1 VM   |           |    Web2 VM   |
     |    Nginx     |           |    Nginx     |
     +--------------+           +--------------+
```

## Technologies

* Vagrant
* VirtualBox
* Ubuntu 22.04
* Ansible
* Nginx

## Project Structure

```
.
├── Vagrantfile
├── inventory
├── playbook.yml
├── ansible.cfg
├── .gitignore
└── README.md
```

## Prerequisites

* Vagrant
* VirtualBox

## Getting Started

Clone the repository:

```bash
git clone https://github.com/matiinmoradi/Vagrant.git
cd Vagrant
```

Start the virtual machines:

```bash
vagrant up
```

Connect to the control machine:

```bash
vagrant ssh control
```

Run the Ansible playbook:

```bash
ansible-playbook -i inventory playbook.yml
```

## Verification

Check that Nginx is running on both web servers:

```bash
systemctl status nginx
```

Or open the web server IP addresses in your browser.

## Learning Objectives

* Provision infrastructure using Vagrant
* Configure multiple virtual machines
* Manage servers with Ansible
* Automate Nginx installation
* Practice Infrastructure as Code (IaC)

## Author

**Matin Moradi**

