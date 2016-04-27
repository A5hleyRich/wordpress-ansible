# WordPress Ansible

This repository contains a playbook for provisioning modern hosting environments geared towards WordPress. It's based on [Hosting WordPress Yourself](https://deliciousbrains.com/hosting-wordpress-setup-secure-virtual-server/) and [WordPress Nginx](https://github.com/A5hleyRich/wordpress-nginx). The following is handled out of the box:

* User setup
* SSH hardening
* Firewall setup

It will also install the following software:

* Nginx with HTTP/2 and [improved default configs](https://github.com/A5hleyRich/wordpress-nginx)
* PHP 7
* MariaDB
* Redis
* WP-CLI
* Fail2Ban
* Git

## Usage

Configure your [hosts file](https://github.com/A5hleyRich/wordpress-ansible/blob/master/hosts).

```
[production]
192.168.1.1 #sampledomain.com
```

Edit [provision.yml](https://github.com/A5hleyRich/wordpress-ansible/blob/master/provision.yml) to configure your default user, [hashed](http://docs.ansible.com/ansible/faq.html#how-do-i-generate-crypted-passwords-for-the-user-module) sudo password and local public key path. This will create a new user on the provisioned servers that you can use to gain SSH access.

Run:

`ansible-playbook provision.yml`