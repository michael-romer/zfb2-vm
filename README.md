# Zend Framework Boilerplate 2 - Virtual Machine Component

## Introduction

This software allows to auto-generate a Virtual Machine capable of running Zend Framework 2
for development purposes. It removes the burden of setting up a LAMP-like environment on your local box.

The following installation instruction assume, you are using [ZendSkeletonApplication](https://github.com/zendframework/ZendSkeletonApplication/).

## Installation

Before you can build your own VM based on the code provided, you will first
need to install some tools on your host box. It somewhat looks like getting all the tools up and running
is even more work than setting up LAMP itself. However, first, installation of tools is really quick & easy
and second, it's a one time effort allowing you to create different LAMP-environments in future easily without messing
up your local system at all (ever worked on 2 projects in parallel, that required a different Apache/PHP setup?).

Here's what you need to do step by step:

- Install Virtual Box
- Install Ruby
- Install Vagrant
- Import Base Box
- Install Zend Framework Boilerplate 2 - Virtual Machine Component

### Install Virtual Box

Head-over to the [Virtual Box Homepage](https://www.virtualbox.org/) and pick the installer matching your
host system. Run it.

### Install Ruby

Head-over to the [Ruby Homepage](http://www.ruby-lang.org/en/downloads/) and pick the installation method of
your choice. On Windows, you will want to use [Ruby Installer](http://rubyinstaller.org/). Run it.

### Install Vagrant

Head-over to the [Vagrant Homepage](http://vagrantup.com/) and pick the installer matching your host system. Run it.

### Import Base Box

Your VM is based on a Ubuntu base installation you will need to download first, before you can build your own
environment on top of it. In a shell, type `vagrant box add precise64 http://files.vagrantup.com/precise64.box`. The
download should start immediately.

### Install Zend Framework Boilerplate 2 - Virtual Machine Component

The recommend way to install the library itself is to use composer. If you're using [ZendSkeletonApplication](https://github.com/zendframework/ZendSkeletonApplication/)
you simply need to add another dependency in `composer.json`:

    "require": {
        "php": ">=5.3.3",
        "zendframework/zendframework": "dev-master#18c8e223f070deb07c17543ed938b54542aa0ed8",
        "zfb/zfb-vm": "dev-master"
    }

Then, run `php composer.phar update`. After download is done, copy `Vagrantfile.dist` from `vendor/zfb/zfb-vm`
to your application root folder and rename it from `Vagrantfile.dist` to `Vagrantfile`. In a shell, change
to your application root folter and type `vagrant up`. Now the VM creation process is in progress (takes a while).
Once done, sfire up a browser and point it to `http://localhost:8080`.