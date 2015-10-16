hosts
=========

Role to manage /etc/hosts file. By default the role wont make any changes if the variable hosts_file not defined.

Role Variables
--------------

```
hosts_file
```

The variable defines the full path to the local hosts file that will be copied to remote as a template.


Example Playbook
----------------

Playbook example of include:

```
- hosts: all
  roles:
   - hosts
```

group_vars/web-servers-atlanta-dc1.yml

```
---
hosts_file: /etc/ansible/group_files/web-servers-atlanta-dc1/hosts/hosts.j2
```

group_files/web-servers-atlanta-dc1/hosts/hosts.j2

```
127.0.0.1      localhost
{{ ansible_default_ipv4.address }}    {{ ansible_fqdn }}  {{ ansible_hostname }}
10.0.0.56      host01.example.org host01
192.168.0.25   host02.example.org host02

# The following lines are desirable for IPv6 capable hosts
::1     localhost ip6-localhost ip6-loopback
ff02::1 ip6-allnodes
ff02::2 ip6-allrouters
```

Author Information
------------------

Tal Lannder

tallannder@gmail.com
