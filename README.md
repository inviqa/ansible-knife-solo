# ansible-knife-solo
Ansible role to run knife-solo

This role runs the [knife-solo][knife-solo] against the provisioned server.

## Requirements
------------
[Knife-Solo][knife-solo] should be installed as prerequisites via a Bundler (Gemfile)
```
gem "knife-solo", "~> 0.5.1"
gem "knife-solo_data_bag", "~> 1.1.0"
```
## Role Variables
------------
#### [`exaple`][example]
Default: none

Description



## Example Playbook
----------------

```YAML
---
- hosts: production
  roles:
     - { role: inviqa.knife-solo}
  vars:
    example: 'value'
...
```
## TODO
- [ ] check that Berkshelf is present
- [ ] run Berkshelf only_once
- [ ] check that `knife solo` is installed and return a meaningful Ansible WARNING (without breaking the provisioning, just abording the run of this role)
- [ ] run `knife solo prepare`
- [ ] run `knife solo cook`
- [ ] test parallelisation

## License
-------

[MIT][licence]

## Author Information
------------------
Authors Hardik Gajjar & Marco Massari Calderone at Inviqa UK Ltd


[github]: https://github.com/inviqa/ansible-knife-solo "Github location of this role"
[knife-solo]: https://matschaffer.github.io/knife-solo/ "knife-solo website"
[example]: https://github.com/inviqa/ansible-knife-solo/blob/master/defaults/main.yml#L4 "Link to variable on master"


[licence]: https://raw.githubusercontent.com/inviqa/ansible-jumpcloud/master/LICENSE
