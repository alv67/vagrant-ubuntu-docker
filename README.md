# vagrant-ubuntu-docker

Prepare a Ubuntu VM to use as a Docker Machine

## Prerequisites

1. Have one Virtual Machine system installed on your system:
    - VirtualBox [www.virtualbox.org] : free for all OS
    - VMWare
    - Parallels
    - ...
2. Install `vagrant` from [www.vagrantup.com]

## Instructions

1. clone this repository
    ```
    git clone https://github.com/alv67/vagrant-ubuntu-docker.git
    ```
2. cd on the folder just created
    ```
    cd vagrant-ubuntu-docker
    ```
3. install **vagrant-docker-compose** plugin
    ```
    vagrant plugin install vagrant-docker-compose
    ```
4. launch command
    ```
    vagrant up
    ```
    to create a start the Virtual Machine

## Other commands

Stop the VM : `vagrant halt`

Delete the VM : `vagrant destroy`

Login into the VM : `vagrant ssh`

Note: if you need more information about the ssh connection to configure direct access to the machine, eg. for remoting VisualStudioCode, please use the command `vagrant ssh-config`

## Use this Ubuntu VM with VSCode Remote-SSH extension?

The **Remote - SSH extension** lets you use any remote machine with a SSH server as your development environment.

First of all you need to install the [Remote - SSH extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh)

The follow the extension documentation for usage.

### Configuring the Host to work with this Ubuntu VM

Since vagrant uses ssh connections ssh-keys, you need to configure the host with correct path for the this _private_key_

Following the Remote-SSH Extension documentation you will know which configuration file you need to modify.

At the moment of writing for me this file is in :

-   `~/.ssh/config` (for Un\*x machines)
-   `c:\Users\[username]\.ssh\config` (for Windows machines)

You must copy in the file the configuration of the vagrant ssh connection:

```
vagrant ssh-config
```

You will see something similar

    Host default
        HostName 127.0.0.1
        User vagrant
        Port 2222
        UserKnownHostsFile /dev/null
        StrictHostKeyChecking no
        PasswordAuthentication no
        IdentityFile [path_to_this_project]/vagrant-ubuntu-docker/.vagrant/machines/default/virtualbox/private_key
        IdentitiesOnly yes
        LogLevel FATAL

If all is ok you can use the VSCode Remote-SSH and develop inside your Ubuntu VM
