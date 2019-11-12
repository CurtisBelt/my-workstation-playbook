# My Workstation Playbook

## Summary

(TODO)

## Usage (Local)

```shell
ansible-playbook --ask-become-pass local.yml
```

## Usage (Remote)

Prepare remote machine:

```shell
sudo dnf install -y openssh-server
sudo systemctl start sshd.service
sudo systemctl enable sshd.service
```
