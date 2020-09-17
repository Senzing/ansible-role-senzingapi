Ansible Role: Senzing API
=========

This role installs Senzing API for Debian and RHEL systems.


Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):

    senzing_g2_release_version: 2.0.0-20197
    senzing_eula:

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
        senzing_eula: <senzing eula value>
      roles:
        - { role: senzing.senzingapi }

Testing Role
----------------
Use the following command to test with molecule

```ansible
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

MIT
