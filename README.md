# Install Ubuntu
This is a VERY opinionated install for Ubuntu. I do not recommend using it as-is, fork and make your changes before using it. You've been warned.

Use Ubuntu Server ISO to install the base OS without any additional package.

## Dependencies
Change the username of the install user on the **group_vars/all** file.

If you are running locally onto a fresh install, there are a few dependencies:

    sudo apt-get install openssh-server sshpass ansible

## Generic tags
There are some tags for generic installations, they are:

* **common**: common installation (haveged, docker, htop, etc...) [(pkgs)](https://github.com/edgard/ansible-edgard/blob/master/roles/common/vars/main.yml)
* **htpc**: common + htpc config (kodi, lirc, etc...) [(pkgs)](https://github.com/edgard/ansible-edgard/blob/master/roles/htpc/vars/main.yml)
* **_myhtpc_**: htpc + my htpc config (nvidia, lirc remote, etc...) [(pkgs)](https://github.com/edgard/ansible-edgard/blob/master/roles/myhtpc/vars/main.yml)

## Example run with tags
    ansible-playbook site.yml --tags "common" -i "localhost," -k

**IMPORTANT: DO NOT FORGET THE COMMA AFTER THE HOST**
