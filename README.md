VM for develop
==============

## Instructions installing development environment

### Install required software for the virtual machine (once pr computer)
1. Install VirtualBox (<https://www.virtualbox.org/wiki/Downloads>)

2. Install Vagrant (<http://www.vagrantup.com/>)

3. Install Vagrant plugin: ```vagrant plugin install vagrant-hostmanager```

4 (Mac). Install Homebrew: ```ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"``` (<http://brew.sh/>)

5 (Mac). Prepare for Ansible: On Mac: Install Xcode from the Mac App Store.

6 (Mac). Install xcode cli (command line) tools with ```xcode-select --install```. On Linux you can use Package Manager (detailed instructions: http://docs.ansible.com/intro_installation.html). On Windows you can use cygwin (https://servercheck.in/blog/running-ansible-within-windows).

7 (Mac). Install Ansible: ```brew install ansible```

7. (Linux) Install Ansible (in Ubuntu sudo apt-get install ansible)

8. Site will be available at http://vm-dev.com/
## Troubleshooting

**Page not found**

Probably an error in the hosts file. Make sure the domain is correct. The following is done on a Mac. Edit the hosts file:

```sudo nano /private/etc/hosts``` (navigate file with arrow keys)

Add ```192.168.100.119	vm-dev.com```

```ctrl+o``` (saves the file)

```ctrl+x``` (exits the editor)

**PHP errors when loading domain**

Refresh the browser.

**Apache default page**

If you are suddenly seeing a default apache ubuntu page instead of the website, this will most likely fix it:

From the root folder of the repo:

```vagrant status``` - Make sure the vagrant is up and running

```vagrant ssh```

```sudo a2dissite 000-default```

```sudo service apache2 restart```

