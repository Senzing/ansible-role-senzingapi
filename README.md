Ansible Role: Senzing API
=========

[![Build Status](https://travis-ci.com/Senzing/ansible-role-senzingapi.svg?branch=master)](https://travis-ci.com/github/Senzing/ansible-role-senzingapi)

This role installs Senzing API for Debian and RHEL systems.

Installation
--------------

Use ansible-galaxy install `senzing.senzing_api` to install the latest stable release of the role on your system.

The following are the supported Senzing API versions.

| Senzing API version|Galaxy version|Path to Install|
|----------|:-------------:|:-------------:|
|2.2.1|2.2.1|`ansible-galaxy install senzing.senzing_api`:2.2.1`|
|2.1.0|2.1.0|`ansible-galaxy install senzing.senzing_api`:2.1.0`|
|2.0.0|2.0.0|`ansible-galaxy install senzing.senzing_api`:2.0.0`|

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):

    senzing_g2_release_version: 2.0.0-20197

Substitute the variables by passing in a variable file.

Dependencies
------------

None.

Example Playbook
----------------

The senzing eula value can be found [here](https://github.com/Senzing/knowledge-base/blob/master/lists/environment-variables.md#senzing_accept_eula)

    - hosts: senzing
      vars:
        senzing_g2_release_version: 2.0.0-20197
      environment:
        SENZING_EULA: '<Insert Senzing EULA here>'
      roles:
        - { role: senzing.senzingapi }

Testing Role
----------------
Use the following command to test this ansible role with molecule

```console
export SENZING_EULA = <Insert Senzing EULA here>
docker run --rm -it \
    --env MOLECULE_NO_LOG="false" \
    -v "$(pwd)":/tmp/$(basename "${PWD}"):ro \
    -v /var/run/docker.sock:/var/run/docker.sock \
    -v ~/.ssh:/root/.ssh \
    -w /tmp/$(basename "${PWD}") \
    quay.io/ansible/molecule:3.0.4 \
    molecule test
```

License
-------

Apache 2

Author Information
------------------

This role was created in 2020 by [Mah Chia Hui](https://github.com/mahchiahui)
