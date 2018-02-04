How to setup the project
========================

### Prerequisites

Please install the following tools on your computer:

*   Git Command Line Client ([Windows](http://git-scm.com/), use [homebrew](http://brew.sh/) on Mac OS X, ...)
*   Install [Virtualbox](https://www.virtualbox.org)
*   Install [Vagrant](https://www.vagrantup.com)
    Vagrant is used to manage the virtual machine running on your computer.
*   Install Vagrant-Plugin [`vagrant-hostmanager`](https://github.com/smdahlen/vagrant-hostmanager)
    This plugin makes sure that your host system is configured with the correct IP of the virtual machine.
    I.e. it adds an entry to `/etc/hosts` (or similar) which maps the VMs IP to `playground.hawdev.de`.
*   Install Vagrant-Plugin [`vagrant-vbguest`](https://github.com/dotless-de/vagrant-vbguest)
    This plugin checks the installed version of the "Virtualbox Guest Additions" and updates it if necessary.

### Configuring Git

You need to make sure that Git doesn't change line endings while fetching files from the repository.

On Linux/Mac OS X this should be the default setting

On Windows you need to explicitly configure this by setting the option `core.autocrlf` to `false`. This can be done (for all projects of the current user)
by running the following command:

    git config --global core.autocrlf false

### Clone the repository

The project repository contains all source code and configuration for the local virtual machine.

    git clone https://github.com/maeg77/chronik-hennstedt.git

### Start the Engine

`vagrant up`

This command starts your personal development VM.

### Installing Dependencies

Use SSH to connect to your virtual machine. You can do this either by typing `vagrant ssh` in the project directory
or by connecting to `playground.hawdev.de` with ssh.

Create the configuration file `app/config/parameters.yml` file by copying `app/config/parameters.yml.dist`.

    cd /opt/symfony
    cp app/config/parameters.yml.dist app/config/parameters.yml
    ant clean-build

Now, you should be able to access the application by opening [chronik-hennstedt.de](http://chronik-hennstedt.de/).

