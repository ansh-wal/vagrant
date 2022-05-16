## Quick Start Guide

### 1 - Install dependencies (Docker, VsCode, Vagrant, Ansible)

  1. Download and install [Docker](https://docs.docker.com/get-docker/).
  2. Download and install [VsCode] (https://code.visualstudio.com/download).
  3. Download and install [Vagrant](http://www.vagrantup.com/downloads.html).
  4. [Mac/Linux only] Install [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html).
  5. Run `ansible-galaxy install -r requirements.yml` in this directory to get the required Ansible roles.
  6. Run `vagrant up --provider=docker --provision` to build the VM.
  7. Run `vagrant ssh-config` this will output valid configuration for an SSH config file to SSH into the running Vagrant machine from ssh directly.
  8. Copy output from above command and paste it in `~/.ssh/config` file
  ```
  cat ~/.ssh/config

  Host node
    HostName 127.0.0.1
    User vagrant
    Port 2222
    UserKnownHostsFile /dev/null
    StrictHostKeyChecking no
    PasswordAuthentication no
    IdentityFile /Users/asharma/git/vagrant/.vagrant/machines/ node/docker/private_key
    IdentitiesOnly yes
    LogLevel FATAL
    ForwardAgent yes
  ```


Note for Windows users: *This guide assumes you're on a Mac or Linux host. Windows hosts are unsupported at this time.*

### 2 - Run Application