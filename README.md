Ansible Challenges Repository
===============================
##Overview
This repo is for the development of some "challenge" type of content related for Ansible. In getting new engineers/ops people started with using Ansible, it can be intimidating. Looking at other playbooks is often a terrible place to start because these are inevitably moderately to highly complex. They are built to take advantage of some features that the beginner will not understand. For example, things that might seem simple 2 weeks into using it, like using variables in a play, will make reviewing other's work extremely difficult to understand. The reason is that a lot of this requires more than a simple knowledge of "this is a variable." It requires the user to know that by default, Ansible will look in specific places for variables and there is an order of preference for how they are included. In my experience, the following principles should apply to learning how to use Ansible.
- Never start from using Ansible Tower. The GUI will make certain things incredibly opaque even when they are straight forward when we are talking about flat yml files and working from the CLI. *ALWAYS START FROM THE CLI*
- Do not look at someone else's work. Their content might actually not be too advanced (like mine), but until you get the fundamentals down it will appear to be the Rosetta Stone.
- Start with a purpose- start working on simple things, but with a purpose (go connect to a host and gather facts; go run yum on the remote target to install 3 packages; etc).

The last note there is really the purpose of this repo- to provide some simple, but increasingly complex, challenges for a newbie to "solve." The goal is to get them up to speed faster so that after a couple weeks they CAN start going and looking at other playbooks, but even for complex ones have the basic knowledge they would need to decipher what the content they are reviewing is designed to do and how it does it. I will attempt to organize this repo into stages of learning (phase1, phase2, etc) where there are a few challenges in each phase. It probably makes sense for each phase to be a file in this directory, and to then provide guidance/answers for each challenge in subdirectories. 

##Usage Instructions
The best thing to do is to clone this repo to your home folder on your control node (see below), and then work from the ansible-challenges directory you'll end up with. Don't worry about making changes in this directory because you do not permission to push those changes up to the remote master. Working from this directory will end up making more sense in the long run as most guidance/answers will assume you are running things from this directory.
- `git clone git@github.com/matts-mpg/ansible-challenges.git`
OR
- `git clone https://github.com/matts-mpg/ansible-challenges.git`
 

##Phases
- Phase 1: Basic Stuff
  - Module 1: Connect to a remote host and collect facts using a one-liner.
  - Module 2: Create the simplest ansible config file possible to avoid problems from here on out.
  - Module 3: Connect to a remote host and collect facts using a simple task file/play.
  - Module 4: Install packages on a remote host.
- Phase 2: Very Simple, Non-threatening Playbooks
  - Module 1: 
  - Module 2: 
- Phase 3: Learning Variables
  - Module 1: Using group_vars.
  - Module 2: Using host_vars.
  - Module 3: Where else can I put vars?
  - Module 4: Using vaulted vars.
- Phase 4: Working With Roles
  - Module 1: 

##Sandbox
This repo includes a Vagrantfile for spinning up machines to use for testing with these challenges. These are defined below.
 Target | Distro | Version | Box                 | 
:------ |:------ | -------:| ------------------- |
host1   | CentOS |  7.1    | bento/centos-7.1    |
host2   | Ubuntu | 16.04   | bento/ubuntu-16.04  |

In order to use this Vagrantfile for these challenges, make sure you have a virtualization provider such as VMware (Fusion or Workstation), Virtualbox, or another [listed on the vagrant site](https://www.vagrantup.com/docs/providers/). [Install vagrant](https://www.vagrantup.com/docs/installation/). Then run `vagrant up` from this directory. After a moment, the boxes should be up and running. Then run `vagrant ssh-config` to get the SSH config options you need to be able to connect to the boxes. Copying the two configuration blocks into your ~/.ssh/config should let you connect to the boxes using `ssh host1` or `ssh host2` unless this conflicts with entries already in your config file.

Lastly, please note that this Vagrantfile specifies VMware Fusion as the provider, so if you use a different one you need to make that small change. For Virtualbox you would simply change the line `node.vm.provider "vmware_fusion" do |vb|` to `node.vm.provider "virtualbox" do |vb|` and then adjust the customization lines. The whole block would look like this:
```node.vm.provider "virtualbox" do |vb|
   vb.memory = 1024
   vb.cpus = 2
end```

##Reference Material
  - [Ansible Documentation Site](http://docs.ansible.com/ansible/): The root site for all Ansible documentation.
  - [Ansible Modules Documentation](http://docs.ansible.com/ansible/modules_by_category.html): Plan to spend a lot of time here. This area of the site has detailed documentation for every Ansible module at your disposal.
  - [Ansible Galaxy](https://galaxy.ansible.com/): Once you start messing around with roles, this is basically a place where Ansible users can share their roles. So, if you want to deploy a basic web server built on RHEL and Apache, there is probably some other user that has created a role for that and shared it through Ansible Galaxy. A primer on Galaxy can be [found here](http://docs.ansible.com/ansible/galaxy.html).
  - [Vagrant Documenation Site](https://www.vagrantup.com/docs/): The site for all Vagrant documentation.
