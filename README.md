# Install Ubuntu
This is a VERY opinionated install for Ubuntu. I do not recommend using it as-is, fork and make your changes before using it. You've been warned.

This has been tested on Ubuntu Trusty, Utopic and Vivid.

* Use **Ubuntu Desktop ISO** for **desktop** role.

## Dependencies
Change the username of the install user on the **group_vars/all** file.

If you are running locally onto a fresh install, there are a few dependencies:

    $ sudo apt-get install software-properties-common
    $ sudo apt-add-repository ppa:ansible/ansible
    $ sudo apt-get update
    $ sudo apt-get install openssh-server sshpass ansible python-pycurl

## Generic tags
There are some tags for generic installations, they are:

* **common**: common installation (haveged, docker, htop, etc...) [(pkgs)](https://github.com/edgard/ansible-ubuntu/blob/master/roles/common/vars/main.yml)
* **desktop**: base + desktop config (repos, chrome, devel, etc...) [(pkgs)](https://github.com/edgard/ansible-ubuntu/blob/master/roles/desktop/vars/main.yml)
* **_mydesktop_**: desktop + personal config (nvidia, sensors, etc...) [(pkgs)](https://github.com/edgard/ansible-ubuntu/blob/master/roles/mydesktop/vars/main.yml)
* **_mymacbook_**: desktop + personal config (tlp, etc...) [(pkgs)](https://github.com/edgard/ansible-ubuntu/blob/master/roles/mymacbook/vars/main.yml)

## Example run with tags
    ansible-playbook site.yml --tags "common" -i "localhost," -k

**IMPORTANT: DO NOT FORGET THE COMMA AFTER THE HOST**
