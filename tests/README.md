Testing based on the work by @geerlingguy
at https://github.com/geerlingguy/ansible-role-test-vms

# Multi-Platform Ansible Role and Playbook Test VMs

Use Vagrant and some VirtualBox boxes that I build to follow the latest releases of the OSes. Currently, you can find the boxes on [Atlas](https://atlas.hashicorp.com/geerlingguy) (they are hosted at [files.midwesternmac.com](http://files.midwesternmac.com/)), and this project runs a playbook against the following OSes:

  - Ubuntu 12.04.x (192.168.3.4)
  - Ubuntu 14.04.x (192.168.3.3)
  - Ubuntu 16.04.x (192.168.3.2)
  - CentOS 6.x (192.168.3.6)
  - CentOS 7.x (192.168.3.5)

The project is extremely simple, and simply requires [Vagrant](https://www.vagrantup.com/), [VirtualBox](https://www.virtualbox.org/), and [Ansible](http://docs.ansible.com/intro_installation.html) to be installed on your host machine.

## Testing a Role
The testing process works as follows:
There are an Ansible Playbook and Inventory configured to spin a bunch of VirtualBox's virtual machines via Vagrant.
Vagrant takes care of all the vms setup and and creation of the required rsa-keys to allow interaction with them.
Ansible will install Chef's Knife in the hostw and VMs and then will run `knife solo cook` against each single vm to provision them with test Chef `site-cookbook` that generates a temporary file inside the vms.

At the end of the provisioning Ansible will run a few test-tasks that will verify if the temporary file has been properly created by the test Chef `site-cookbook` and will prompt with the result of the verification.

this is the command to start the testing process the use of the `-l <inventory_hostname>` parameter is optional and is useful to run the test on a specific vm instead of all of them.

```
cd  ./tests
ansible-playbook -i inventory [ -l centos6,centos7,ubuntu1202,ubuntu1402,ubuntu1602 ] playbook.yml
```

This command is to to run a playbook which will instruct Vagrant to destroy the testing vms.
```
cd  ./tests
ansible-playbook -i inventory [ -l centos6,ubuntu1402 ] playbook_delete_vms.yml

```

## License

MIT

## Author Information

Created in 2014 by [Jeff Geerling](http://jeffgeerling.com/), author of [Ansible for DevOps](http://ansiblefordevops.com/).
