# Terminus Dev VM
## Overview
This is a preconfigured setup to do terminus dev.

## Prerequisites
- Docker (https://docker.com)
- Docksal (https://docksal.io)

## Getting started
- Clone the repo anywhere on your system
- If you need Docker + Docksal, there are scripts to install in /scripts folder
  - ./install-docker.sh
  - ./install-docksal.sh
- Run a `composer install` to install terminus deps
- Run a `fin up` and it should initialize everything, you'll see links to the IDE:
```
fin up
Starting services...
Creating network "terminus-vm_default" with the default driver
Creating volume "terminus-vm_cli_home" with default driver
Creating volume "terminus-vm_db_data" with default driver
Creating terminus-vm_db_1  ... done
Creating terminus-vm_cli_1 ... done
Creating terminus-vm_ide_1 ... done
Creating terminus-vm_web_1 ... done
Connected vhost-proxy to "terminus-vm_default" network.
Waiting for project stack to become ready...
Waiting for project stack to become ready...
Project URL: http://terminus-vm.docksal
Web IDE URL: http://ide-terminus-vm.docksal

```
- In the IDE, it should be ready to set breakpoints and run xDebug as needed. 
- Use `fin bash` to invoke `vendor/bin/terminus` from within the container, which will properly route to xDebug in the browser.