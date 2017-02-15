Role Name
=========

An [Ansible] role to install [MongoDB]

Requirements
------------

Role Variables
--------------

```
---
# defaults file for ansible-mongodb
mongodb_apt_keyserver: 'keyserver.ubuntu.com'
mongodb_apt_gpg_key: 'EA312927'
mongodb_debian_apt_repo: 'deb http://repo.mongodb.org/apt/{{ ansible_distribution|lower }} {{ ansible_distribution_release }}/mongodb-org/{{ mongodb_version }} main'
mongodb_ubuntu_apt_repo: 'deb http://repo.mongodb.org/apt/{{ ansible_distribution|lower }} {{ ansible_distribution_release }}/mongodb-org/{{ mongodb_version }} multiverse'
mongodb_version: '3.2'
mongodb_redhat_repo_info:
  name: 'MongoDB-Repository'
  description: 'MongoDB-Repository'
  baseurl: 'https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/{{ mongodb_version }}/x86_64/'
  gpgcheck: yes
  enabled: yes
  gpgkey: 'https://www.mongodb.org/static/pgp/server-{{ mongodb_version }}.asc'
```
Dependencies
------------

None

Example Playbook
----------------
```
---
- hosts: test-nodes
  become: true
  vars:
    pri_domain_name: 'test.vagrant.local'
  roles:
    - role: ansible-mongodb
  tasks:
```

License
-------

BSD

Author Information
------------------

Larry Smith Jr.
- @mrlesmithjr
- http://everythingshouldbevirtual.com
- mrlesmithjr [at] gmail.com

[Ansible]: <https://www.ansible.com>
[MongoDB]: <https://www.mongodb.org/>
