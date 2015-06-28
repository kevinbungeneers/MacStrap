# MacStrap
MacStrap is a collection of Ansible roles to configure your Mac.

## Requirements
If you're planning on just invoking `ansible-playbook macstrap.yml --ask-sudo-pass` you'll need to have Homebrew and Ansible installed. The oneliner, meant for setting things in motion after a fresh install, installs both of them for you.

## What's included?
This is all very personal. If you choose to use MacStrap you'll probably end up forking this repo to make it your own.

My setup contains:
* ZSH (with [prezto](https://github.com/kevinbungeneers/prezto))
* boot2docker with docker-compose
* Sublime Text 3
* Atom
* Virtualbox
* Vagrant
* Packer
* ...
* Fancy tweaks
* More fancy tweaks

Some applications got their own role because they needed configuration or support the installation of plugins. Others are simply installed in the Homebrew role.

## Getting started
First things first: fork this repository and make the proper adjustments to `variables/common.yml`

Before kicking this thing in action it might be advisable to check out some of the roles to see what exactly is getting installed and how things are getting configured.

After you've checked out the roles and made your adjustments, execute the following from within the directory:
```bash
$ ansible-playbook macstrap.yml --ask-sudo-pass
```
or, if you've just installed a fresh copy of OS X:
```bash
$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/kevinbungeneers/MacStrap/master/install)"
```
