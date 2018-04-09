# ansible-knife-solo
Ansible role to run knife-solo

This role runs [knife-solo][knife-solo] against the provisioned server.

## Requirements
------------
[Knife-Solo][knife-solo] should be installed as prerequisites via a Bundler (Gemfile)
```
gem "knife-solo", "~> 0.5.1"
gem "knife-solo_data_bag", "~> 1.1.0"
```
## Role Variables
------------
#### chef_use_root
Default: false

When set to true forces `chef_user` to be `root`

#### chef_user
Default: #{ansible_user}

Define the user using which knife solo should run. It must be a sudo user.
If `chef_use_root` is true `chef_user` is ignored and forced to `root`.
If not specified it will use the host's system use `ansible_user`.

#### chef_dir
Default: ../chef

Path to your chef directory where knife solo should run.

#### run_knife_solo_prepare
Default: True

run `knife solo prepare` against the provisioned host

#### run_knife_solo_cook
Default: True

run `knife solo cook` against the provisioned host

## Example Playbook
----------------

```YAML
---
- hosts: production
  roles:
     - { role: inviqa.knife-solo}
  vars:
    run_knife_solo_cook: true
...
```

## Testing
See README file in the `tests` directory

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
