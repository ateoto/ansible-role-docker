ansible-role-docker
===================

This is a reusable role to deploy docker using ansible.

Tested against Ubuntu LTS and Debian stable.


Installation
------------

Not currently on ansible galaxy, so you'll need to use from github. Two ways
you can do this, you can add the following to your meta/requirements.yml if you are
already using a role that requires docker.

```yaml
- src: https://github.com/ateoto/ansible-role-docker
  name: ateoto.docker
```

Alternatively, you can clone this repository locally and add it to your
ansible role path.

This is how I have my ```bash ~/.ansible.cfg ``` setup for roles.

```bash

roles_path = /etc/ansible/roles:/Users/ateoto/code/ansible-roles
```

Then you could just clone to:

```bash
$ cd ~/Code/ansible-roles
$ git clone https://github.com/ateoto/ansible-role-docker ateoto.docker

```

Usage
-----

If you specify a DOCKER_AUTH and DOCKER_EMAIL variable, this role will generate
a config.json file for you. The DOCKER_AUTH string is a base64 encoded string in
the format of ``` DockerHubUsername:DockerHubPassword ```. To generate this
you can either login to DockerHub locally and grab the auth string from
``` ~/.docker/config.json``` or you can use bash or a programming language of some kind.


Example in bash:

```bash
$ echo ateoto:t3rriblepass | base64 -i -
YXRlb3RvOnQzcnJpYmxlcGFzcwo=
```

