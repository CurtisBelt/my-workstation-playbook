# My Workstation Playbook

## Summary

(TODO)

## Usage (Local)

```sh
ansible-playbook --ask-become-pass local.yml
```

## Usage (Remote)

https://linuxhint.com/ssh_local_machine_virtual_kvm_centos/

**Prepare remote machine:**

```sh
sudo dnf install -y openssh-server
sudo systemctl enable --now sshd
# Get IP
hostname -I
```

**/etc/ansible/hosts**

```
[fedora]
192.168.122.13

[fedora:vars]
# Technically, on Fedora 35, python is symlinked to python3 - but setting this will avoid "[DEPRECATION WARNING]: Distribution fedora 35 on host 192.168.122.13 should use /usr/bin/python3, but is using /usr/bin/python for backward compatibility with prior Ansible releases.".
ansible_python_interpreter=/usr/bin/python3
```

**Local Machine**

```sh
ansible-playbook local.yml --ask-pass --ask-become-pass
```


## TODO:

- How to use vault for secrets
- What's the best way to handle updating configuration files?
