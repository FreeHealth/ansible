## Ansible playbook

This playbook has been tested for server edition of Ubuntu 16.04, 17.04 and 17.10.

It should also work for Debian (untested).

It will:

  * install a basic Desktop Environment (LXDE)
  * change keymap
  * install MariaDB server
  * add a MariaDB user (username and password: fhio)
  * install FreeHealth EHR packages 

### Run the playbook

ansible-playbook --become -i hosts.ini site.yml --extra-vars "ppa=nightly"

The hosts file (hosts.ini) is meant to work out of the box for a Packer/Vagrant
VM built with our packer-templates builds.

### Access VM through ssh
Testing should be done through the (VirtualBox) GUI but you can also access
through SSH and keep working from your favourite terminal (and screen resolution).

You can add you **public** ssh key as a file inside roles/ssh/files to get
passwordless access to the running VM.

ssh -p2222 vagrant@127.0.0.1

### Settings

#### Keymap

Modify the default keymap (fr) in:
    vars/main.yml

Just replace fr by en
