KVM.ACL Fix
=========

# Solution:
https://forum.manjaro.org/t/virt-manager-doesnt-work-permission-denied/108142

Works:
>anon51566685
>Libvirt is using libvirt-qemu group now and not nobody anymore, as far as I can tell.
>Try setting +x ACL on $HOME, Documents and VirtualBox\ VMs, and any other appropriate dirs: `setfacl -m user:libvirt-qemu:--x /path/to/dir`

## example:
```
setfacl -m user:libvirt-qemu:--x /home/me/.uni/iso
```
if this doesn't work try to set it for Every parent directory!


# Error
from: kvm "node-name":"libvirt-1-storage","auto-read-only":true,"discard":"unmap"}: Could not open

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
