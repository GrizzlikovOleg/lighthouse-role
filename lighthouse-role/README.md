lighthouse
=========

This role installs and configures LightHouse, an open-source monitoring solution. It handles the installation of the required static files, the configuration of Nginx to serve the LightHouse web interface, and starts the Nginx service.

Requirements
------------

- The target system must have Nginx installed (or it will be installed by this role).
- The lighthouse_version variable must be specified (default is latest).
- A lighthouse_nginx.conf.j2 template for Nginx should be available for customization.

Role Variables
--------------

- lighthouse_version: Defines the version of LightHouse to install (default is latest).
- ighthouse_nginx_conf: Path to the Nginx configuration file to serve the LightHouse web interface (default is /etc/nginx/conf.d/lighthouse.conf).

Dependencies
------------

nginx will be installed with this role.

Example Playbook
----------------

---
- name: Install and configure LightHouse  
  hosts: your's hostname  
  become: true  
  roles:  
    - { role: GrizzlikovOleg.lighthouse-role, lighthouse_version: "latest", lighthouse_nginx_conf: "/etc/nginx/conf.d/lighthouse.conf" }

if you use req.yml

- name: Install and configure LightHouse  
  hosts: your's hostname  
  gather_facts: true  
  roles:  
    - lighthouse  

License
-------

MIT

Author Information
------------------

GrizzlikovOleg for Netology only
