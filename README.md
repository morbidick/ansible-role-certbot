# Install certbot with Ansible

[![Build Status](https://travis-ci.org/morbidick/ansible-role-certbot.svg?branch=master)](https://travis-ci.org/morbidick/ansible-role-certbot)

Installs certbot and configures certificates. For a complete setup with nginx see [the full example](https://github.com/morbidick/ansible-role-certbot-vhosts/blob/master/webserver.md).

## Requirements

None.

## Example playbook

````yaml
- hosts: all
  become: yes

  roles:
  - certbot

  vars:
    certbot_mail: me@example.com
    certbot_certs:
      - host: example.com
      - host: foo.bar
        mail: overwrite@mail.com
````

## Role variables

None of the variables below are required.

| Variable                 | Default   | Comment |
| :---                     | :---      | :---    |
| certbot_mail             |           | *required* the account email |
| certbot_certs            | `[]`      | list of certs to request |

For all options see [defaults/main.yml](defaults/main.yml)

## Development

You can use the [Vagrantfile](Vagrantfile) for local testing, just install vagrant and virtualbox and execute the following commands:

````bash
vagrant up
vagrant provision
````

## License

MIT
