# OpenFaaS Sandbox
This vagrant file can be used to create an OpenFaaS sandbox (deployed to Docker Swarm).

## Installation

1) Download the latest VirtualBox installer from [here](https://www.virtualbox.org/wiki/Downloads).
2) Run VirtualBox installer with defaults.
3) Download the latest Vagrant installer from [here](https://www.vagrantup.com/downloads.html).
4) Run the Vagrant installer with defaults.
5) From the command prompt, run the following to create the VM:
```sh
vagrant up
```

## Using OpenFaaS

### CLI

For simplicity, the [OpenFaaS CLI](https://github.com/openfaas/faas-cli) should be accessed from the sandbox itself - Windows requires a [package manager](https://github.com/lukesampson/scoop) installing before the CLI can be installed.

Use the following to connect to the VM:

```sh
vagrant ssh
```

Once connected run the following for help:

```sh
faas --help
```

The "data" folder in this repo is mapped to "/vagrant_data" on the VM. Therefore any data (e.g. code for functions) copied here will be accessible from the CLI within the VM.

### UI

The OpenFaas UI is accessible using [here](http://localhost:8080/ui/). The Prometheus UI can also be accessed [here](http://localhost:9090/graph).