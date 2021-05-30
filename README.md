# vagrant-ubuntu-docker
Prepare a Ubuntu VM to use as a Docker Machine

## Prerequisites
1. Have one Virtual Machine system installed on your system:
    - VirtualBox [www.virtualbox.org] : free for all OS
    - VMWare
    - Parallels
    - ...
2. Install `vagrant` from  [www.vagrantup.com]

## Instructions

1. clone this repository
    ``` 
    git clone https://github.com/alv67/vagrant-ubuntu-docker.git        
    ```
2. cd on the folder just created
    ```
    cd vagrant-ubuntu-docker
    ```
3. launch command 
    ```
    vagrant up
    ```
    to create a start the Virtual Machine

## Other commands

Stop the VM : `vagrant halt`

Delete the VM : `vagrant destroy`

Login into the VM : `vagrant ssh`

Note: if you need more information about the ssh connection to configure direct access to the machine, eg. for remoting VisualStudioCode, please use the command  `vagrant ssh-config`