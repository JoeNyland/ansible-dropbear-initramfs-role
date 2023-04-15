joenyland.dropbear_initramfs
=========================

[![CI](https://github.com/JoeNyland/ansible-dropbear-initramfs-role/actions/workflows/ci.yml/badge.svg)](https://github.com/JoeNyland/ansible-dropbear-initramfs-role/actions/workflows/ci.yml)

Installs dropbear-initramfs and configures it.

Requirements
------------

None.

Role Variables
--------------

### `dropbear_initramfs_ssh_authorized_keys`

The keys to allow access to dropbear in [this](https://docs.ansible.com/ansible/latest/collections/ansible/posix/authorized_key_module.html#parameter-key) format.

### `dropbear_initramfs_options`

Options to set against the key `DROPBEAR_OPTIONS` in `/etc/dropbear-initramfs/config`

For example, to have `zfsunlock` be automatically be run in initramfs, you could set:

```yaml
dropbear_initramfs_options: '-c /usr/bin/zfsunlock'
```

Which would result in the following to be set in `/etc/dropbear-initramfs/config`:

```
DROPBEAR_OPTIONS='-c /usr/bin/zfsunlock'
```

Dependencies
------------

None.

Example Playbook
----------------

```yaml
- hosts: server
  roles:
    - joenyland.dropbear_initramfs
```

License
-------

MIT

Author Information
------------------

⌨️ with ❤️ by [Joe Nyland](https://joe.nyland.io)
