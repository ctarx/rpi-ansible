# rpi-ansible
> Initial setup of a Raspberry Pi with Ansible

## Install Raspberry Pi OS

I install Raspberry Pi OS using Raspberry Pi Imager
```shell
$ sudo apt install rpi-imager
```
`shift+ctrl+x` for an advance options and setup:
- hostname
- disable overscan
- authorized_keys
- username and password
- wifi
- locale
- keyboard layout
- skip first-run wizard

## Ansible
```shell
$ ansible-playbook run.yml
```

## Extras
LCD-show for 3.5inch RPi Display
```shell
$ cd tasks
$ ansible-playbook lcd.yml
```

#### Contact
Created by [@ctarx](https://linuxrocks.online/@ctarx) - feel free to contact me!
