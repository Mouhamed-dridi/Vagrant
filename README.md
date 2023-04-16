# Vagrant Quick Start Guide

Vagrant is an open-source tool that allows you to create and configure lightweight, reproducible, and portable development environments. This quick start guide will provide you with the basic commands to get started with Vagrant.

## Installation

Before using Vagrant, you need to install it on your computer. You can download and install Vagrant from the official website vagrantup.com.

## Getting Started

To get started with Vagrant, follow these simple steps:

Create a directory for your project:

```
$ mkdir my-project
$ cd my-project
```

Initialize Vagrant in the directory:
```
$ vagrant init
```



This will create a Vagrantfile in your directory that contains the basic configuration for your Vagrant environment.

Start the Vagrant environment:
```
$ vagrant up
```

## Vagrant Box
A Vagrant box is a pre-configured and reusable virtual machine image that contains an operating system, software, and other necessary dependencies. Vagrant boxes are typically used to quickly set up a development environment for a project without having to manually install and configure everything from scratch.
```
vagrant box add --insecure hashicorp/precise64
```

## Get More Vm box From Vgarant hub 
Vagrant Hub is a web-based service provided by HashiCorp that allows users to discover, share, and use Vagrant boxes. Vagrant Hub provides a central repository for Vagrant boxes, making it easy to find and use boxes created by other users or organizations.
To use Vagrant Hub, you need to have a Vagrant account. You can sign up for a free account at https://app.vagrantup.com. 

## VagrantFile
A Vagrantfile is a configuration file that defines the settings and configuration for a Vagrant environment. It specifies details such as the base box to use, network settings, synced folders, and other virtual machine settings.
Creating a Vagrantfile is relatively simple.
Edit the Vagrantfile using a text editor to configure your Vagrant environment. Here's an example Vagrantfile that uses the "hashicorp/bionic64" box:
```
Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/bionic64"
  config.vm.network "private_network", ip: "192.168.33.10"
  config.vm.synced_folder ".", "/vagrant", disabled: true
end
```
This Vagrantfile sets the box to "hashicorp/bionic64", assigns the virtual machine a private IP address of "192.168.33.10", and disables synced folders.

## Run 
You can now use the vagrant up command to create and start your Vagrant environment. Vagrant will use the Vagrantfile to provision and configure the virtual machine, based on the settings you specified. You can modify the Vagrantfile as needed to adjust the configuration of your Vagrant environment.

## Vagrant and Vmwear
You can use Vagrant with VMware by installing the vagrant-vmware-desktop plugin, which provides support for VMware Workstation and Fusion.
Here are the steps to use Vagrant with VMware:
Install VMware Workstation or Fusion on your computer.
Install the vagrant-vmware-desktop plugin by running the following command:
```
vagrant plugin install vagrant-vmware-desktop
```

This will install the plugin that provides support for VMware.
Create a Vagrantfile for your environment, specifying the VMware provider. Here's an example Vagrantfile that uses the "hashicorp/bionic64" box with VMware:
```
Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/bionic64"
  config.vm.provider "vmware_desktop" do |v|
    v.memory = 1024
    v.cpus = 2
  end
end

```
This Vagrantfile sets the box to "hashicorp/bionic64" and specifies that it should use the VMware provider with 1GB of memory and 2 CPUs.
Start the virtual machine by running the following command:
```
vagrant up --provider=vmware_desktop

```
#  ssh to the Vm
Once the virtual machine is up and running, you can use the vagrant 'ssh command 'to connect to it via SSH.


