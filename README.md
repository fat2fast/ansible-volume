Setup partition and Volume Group , Extend Volume Group
===================
This playbook helps you create partitions, physical volumes, volume groups, logical volumes, and extend existing partitions to a volume group

Requirements
------------

- **Ansible**: Ensure Ansible is installed on your control machine.
- [**Logical Volume Manager version 2 (LVM2)**](https://packages.debian.org/source/buster/lvm2): Install it on target systems. You can install it using `apt`:
```bash
sudo apt update
sudo apt install lvm2
```
- Update the variables in the files [volume_group_init.yml](./volume_group_init.yml) and [volume_group_extend.yml](./volume_group_extend.yml) to match your environment.
- Create an inventory file specifying the target hosts.Create an inventory file.

Role Variables
--------------

- `devices`: A list of disks to be partitioned.
- `vg_name`: The name of the volume group.
- `lv_name`: The name of the logical.
- `mount_point` : The path where the logical volume will be mounted.

Example Playbook
----------------
### Initialize Volume Group

Run the following command to create a new volume group:
```bash
ansible-playbook volume_group_init.yml -i your_inventory.ini
```
### Extend Volume Group
Run the following command to extend an existing volume group:

```bash
ansible-playbook volume_group_extend.yml -i your_inventory.ini
```
License
-------

[Detail](./LICENSE)

Author Information
------------------

[Fat2Fast](https://github.com/fat2fast)