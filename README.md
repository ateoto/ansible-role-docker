ansible-role-docker
===================

This is a reusable role to deploy docker using ansible.

Tested against Ubuntu LTS and Debian stable, as of 2015-08-24 the role has been updated
to reflect changes in Docker repo, installing docker-engine.


Installation
------------

```bash
ansible-galaxy install ateoto.docker
```



Usage
-----

If you specify a docker_auth and docker_email variable, this role will generate
a config.json file for you. The docker_auth string is a base64 encoded string in
the format of ``` DockerHubUsername:DockerHubPassword ```. To generate this
you can either login to DockerHub locally and grab the auth string from
``` ~/.docker/config.json``` or you can use bash or a programming language of some kind.


Example in bash:

```bash
$ echo ateoto:t3rriblepass | base64 -i -
YXRlb3RvOnQzcnJpYmxlcGFzcwo=
```

Roadmap
-------

- Support for all Debian/Ubuntu platforms
- Support for installing other Docker components (machine/swarm)
