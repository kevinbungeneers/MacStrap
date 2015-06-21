# MacStrap
MacStrap is a collection of Ansible roles to configure your Mac.

## Requirements
You'll need to have your devtools or Xcode installed.

## What's included?
This is all very personal. If you choose to use MacStrap you'll probably end up forking this repo to make it your own.

My setup contains:
* ZSH (with prezto)
* boot2docker with docker-compose
* Sublime Text 3
* Vagrant
* Packer
* Fancy tweaks
* More fancy tweaks

Some applications got their own role because they needed configuration or support the installation of plugins. Others are simply installed in the Homebrew role.

## Getting started
First things first: fork this repository and make the proper adjustments to `variables/common.yml`

Before kicking this thing in action it might be advisable to check out some of the roles to see what exactly is getting installed and how things are getting configured.

After you've checked out the roles and made your adjustments, execute the following from within the directory:
```bash
$ rake install
```
