Ubuntu Ansible
==============

|TravisCI|

Configure a Ubuntu machine using usual tools and applications installed.
After installing a fresh Ubuntu installation all you need to do is install ansible:

::

    sudo apt-get install python-pip
    sudo pip install ansible

Once thats done then run one of the playbooks found in this repo.

``ubuntu_role.yml`` is used for setting up Repo, Package Install and  Ubuntu Gnome environment using Gnome Shell.

For example, setting up a machine with Ubuntu playbook would be done as follows:

::

    ansible-playbook ubuntu_role.yml   Optional inentory and sudo privileges:ansible-playbook ubuntu_role.yml  -i local.inventory --ask-sudo-pass
    ansible-playbook -vvvv ubuntu_role.yml

This will prompt you for your user password, your Git username, your Git email address (this is to set up your git configuration correctly) and finally your gpg key id.

The user you run this as must have sudo priveleges for this playook to run successfully due to installing system wide applications.

This repo is currently designed so that core UNIX tools like curl and git which are purely terminal based and not dependent on any desktop environment are separated from UI based applications. Currently it is organised using roles as follows:

- Ubuntu: core Ubuntu Linux tools
- Developer: developer specific packages
- Gnome: Gnome core-related settings and applications
- Gnomeshell: Gnome shell specific configurations.

Further desktop environment roles may be added in the future (e.g. gnome, kde etc...)

The playbooks provided in this repo are currently being tested on a Ubuntu Gnome 16.04, 18.04.4 Bionic machine

