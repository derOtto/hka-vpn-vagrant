# Create and run VM with HKA VPN
Vagrantfile with Ansible provisioning for setting up Ubuntu VM with running HKA VPN-Connection.

## Requirements
* [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
* [Vagrant](https://www.vagrantup.com/downloads)
* [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) (There are multiple ways to install, but I would propose to install Python3 and pip3 and following the Installation below
  )

## Installation
With pip3 installed:
```bash
pip3 install ansible
pip3 install molecule[lint,docker]  # only for development / testing
```

Then install required galaxy roles:
```bash
ansible-galaxy install -r requirements.yml
```

For running the molecule tests, docker also needs to be installed.

## VPN credentials
In the cloned directory (you will be asked for an encryption pass):
```bash
ansible-vault create hka-credentials.yml
```
and paste your credentials like this (ATTENTION: credentials will be stored unencrypted on guests vpnc conf in /etc/vpnc directory):
```yaml
iz_user: mami1011  # IZ-Username
iz_pass: thisisnotasafepassword  # IZ-Pass
```

## Start
Start the vm (in the cloned directory):

```bash
vagrant up
```

First time you run this, this will take some time to download the box.
You will than asked for your vault password to unencrypt your credentials locally.
**Please don't login until the provisioning has been finished.**

The password for the user vagrant should be *vagrant*.

You could now also suspend, halt, resume, destroy … the machine (just type *vagrant* for all options).

## TODO
* testing
* todos in main.yml playbook
* …

## License
[MIT](https://choosealicense.com/licenses/mit/)
