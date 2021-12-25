# Raspberry Valley Ansible

## Introduction

This repository contains our Ansible setup scripts for deploying a lot of Raspberry Pi devices. 

We consider Ansible to be always work in progress, and this repo proves it! So please adjust to your liking, these are just simple templates.

# Installation

Our Ansible setup is aimed at a vanilla Raspberry Pi OS image. The intention is to have no manipulation at all with the base image.

* Flash images of Raspberry Pi devices and enable SSH. All other settings are managed by Ansible. Connect the Raspberry Pis to the network and note down their IP addresses
* navigate to *inventories/hosts* and configure the IP addresses of the Raspberry Pi devices connected. This hostfile expects an inventory short name, IP and logon settings, where the inventory short name is later set as a hostname of each device
* Navigate to defaults and copy **secrets.yml.example** to **secrets.yml**. Update with your configuration
* Launch one of the playbooks available

Currently, we have the following playbooks for installations:

*  **main** - this playbook contains most of the software we typically install on our Raspberry Pi devices. The software packages can be configured and/or enabled in the defaults configuration file
* **base-config** - run the basic configuration role with some sensible defaults (see *rpi-config* role)
* **docker-swarm** - a playbook to deploy software for several devices in Docker Swarm mode
* **poweroff** - use a playbook to power off all your devices at once. Of course this does throw an error (as it should), but it does the job and brings some extra convenience
* **reboot** - a playbook to simply reboot all your devices

Further, you can find some more available tasks in the *tasks* directory, which are not used in any playbook and are here for convenience, or to be used in special cases.

* **mosquitto** - you can setup a local Mosquitto broker (we use Docker Mosquitto instead)
* **nodered** - setup a local Node-RED instance (we use Node-RED via Docker instead)

## Missing features

Here are some features which are work in progress and which will be added.

* pi password changed (however SSH is handled)
* pyenv
* log2ram

## About

Raspberry Valley is a maker community in Karlskrona, Sweden. We run makerspaces every week, working with Raspberry Pis, Arduinos and other interesting hardware.

This repository is here to support our community of makers. A lot of our achievements are based and inspired by the community at large. We wish to pay back and share our experiences and lessons learned. Join us!

You can find our pages here: [Raspberry Valley](https://raspberry-valley.azurewebsites.net). You can also join us on [Twitter](https://twitter.com/RaspberryValley) or check [Docker Hub](https://hub.docker.com/r/raspberryvalley/) for images of interest.

## Links

Credits

* [ansible-dockerswarm-raspi](https://github.com/johnbarney/ansible-dockerswarm-raspi?utm_source=pocket_mylist) - our Docker Swarm is inspired by this repo by John Barney

Raspberry Valley makerspace links

* [Raspberry Valley](https://raspberry-valley.azurewebsites.net) - Other things we make and do
* [Raspberry Valley on Twitter](https://twitter.com/RaspberryValley)
* [Raspberry Valley on Github](https://github.com/raspberryvalley)
* [Raspberry Valley Docker Hub Images](hub.docker.com/r/raspberryvalley/)
