Ansible Role: Senzing API
=========

This role installs Senzing API for Debian and RHEL systems.


Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):

    senzing_project_dir: /var/senzing
    senzing_g2_release_version: 2.0.0-20197
    senzing_project_create: N
    senzing_eula:

Substitute the variables by passing in a variable file.

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: senzing
      vars:
        senzing_g2_release_version: 2.0.0-20197
        senzing_eula: I_ACCEPT_THE_SENZING_EULA
        senzing_project_create: Y
        senzing_project_dir: /var/senzing
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

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
