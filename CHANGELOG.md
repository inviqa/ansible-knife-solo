## v0.2
- [X] check that Berkshelf is present
- [X] run `knife solo prepare` [optional]
- [X] run `knife solo cook` [optional]
- [X] check that `knife solo` is installed and return a meaningful Ansible WARNING (without breaking the provisioning, just abording the run of this role)
- [X] test parallelisation
- [X] add testing environment
- [X] complete the testing for all the platforms
- [X] write the documentation
- [X] add the use of `ansible_ssh_args: '-o StrictHostKeyChecking=no'` in the testing playbook to prevent issue with the  provisioning of the newly created vagrant VMs
