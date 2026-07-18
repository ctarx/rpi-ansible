# rpi-ansible
>
> Initial setup of a Raspberry Pi with Ansible

## Install Raspberry Pi OS

Install Raspberry Pi OS using Raspberry Pi Imager:

```shell
sudo apt install rpi-imager
```

Press `Shift+Ctrl+X` to open the advanced options and configure:

- hostname
- disable overscan
- authorized_keys
- username and password
- wifi
- locale
- keyboard layout
- skip first-run wizard

The inventory uses the `pi` account by default. If you choose another user,
update `ansible_user` in `hosts` before running Ansible.

## Ansible

Update the host address in `hosts`, then install the SSH key for the same user
that Ansible will use:

```shell
ssh-copy-id -i ~/.ssh/ansible.pub pi@192.168.1.10
ansible-playbook run.yml
```

Add `--ask-become-pass` if the remote user requires a password for `sudo`.

## Extras

Configure an LCD-show compatible 3.5-inch Raspberry Pi display:

```shell
ansible-playbook lcd.yml
```

The LCD playbook supports both the current `/boot/firmware` layout and the
legacy `/boot` layout. It reboots the Raspberry Pi only when a boot setting
changes.

## Contact

Created by [@ctarx](https://web.libera.chat/) - feel free to contact me!
