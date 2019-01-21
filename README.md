# Ansible ndench.fakesqs role

[![Build Status](https://img.shields.io/travis/ndench/ansible-role-fakesqs.svg)](https://travis-ci.org/ndench/ansible-role-fakesqs)
[![Galaxy](http://img.shields.io/badge/galaxy-ndench.fakesqs-blue.svg)](https://galaxy.ansible.com/ndench/fakesqs)
[![GitHub Tags](https://img.shields.io/github/tag/ndench/ansible-role-fakesqs.svg)](https://github.com/ndench/ansible-role-fakesqs)

> `ndench.fakesqs` is an [Ansible](http://www.ansible.com) role which:
>
> * installs [fakesqs](https://github.com/jubos/fake-s3)
> * configures fakesqs service
> * (optional) create fakesqs queue
> * allows development against the SQS API

## Installation

Using `ansible-galaxy`:

```shell
$ ansible-galaxy install ndench.fakesqs
```

Using `requirements.yml`:

```yaml
- src: ndench.fakesqs
```

Using `git`:

```shell
$ git clone https://github.com/ndench/ansible-role-fakesqs.git ndench.fakesqs
```

## Dependencies

* Ansible >= 2.4
* {"role"=>"geerlingguy.ruby", "become"=>true}

## Variables

Here is a list of all the default variables for this role, which are also available in `defaults/main.yml`.

```yaml
---
fakesqs_gem: fake_sqs
fakesqs_service_enabled: yes
fakesqs_service_state: started

# Whether to create a queue
fakesqs_create_queue: true
fakesqs_queue_name: sqs_dev


```


## Usage

This is an example playbook:

```yaml
---
- hosts: all
  roles:
    - ndench.fakesqs

```

# TODO

* get docker build working (vagrant works fine)
  * issue is to do with docker not being able to run systemd or upstart

## Testing

```shell
$ git clone https://github.com/ndench/ansible-role-fakesqs.git
$ cd ansible-role-fakesqs
$ make test
```

## Contributing
In lieu of a formal style guide, take care to maintain the existing coding style. Add unit tests and examples for any new or changed functionality.

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

*Note: To update the `README.md` file please install and run `ansible-role`:*

```shell
$ gem install ansible-role
$ ansible-role docgen
```

## License
Copyright (c)  under the MIT license.
