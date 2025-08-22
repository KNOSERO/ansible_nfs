# ansible_nfs
Script for installing and configuring nfs in Ansible

## Example

```yaml
---
- name: Install nfs
  hosts: all
  become: yes
  vars:
    nfs_shares:
      - { server_ip: "192.168.0.2", remote: "/nfs1", local: "/mnt/nfs1" }
      - { server_ip: "192.168.0.3", remote: "/nfs2", local: "/mnt/nfs2" }

  tasks:
    - name: Run mount_nfs.yml
      include_tasks: ./task/ansible_nfs/playbook.yml
```