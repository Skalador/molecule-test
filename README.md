# Molecule Example for Ansible

This directory contains an example Molecule configuration for an Ansible playbook that allows easy development and testing of the playbook.

The Molecule configuration can be run locally or in a Continuous Integration (CI) environment, to ensure the playbook is always working correctly.

To run the Molecule environment, you must have `molecule` (with it's `docker` plugin), `ansible`, and the `docker` Python library installed:

    pip3 install ansible molecule molecule-plugins[docker] docker

Additionally, there are lint tools configured to ensure code formatting is correct, so you need to make sure the lint tools are installed:

    pip3 install yamllint ansible-lint

Once everything is ready, run:

    molecule test

This will run the test on two different images:
- [Rocky Linux 8](https://github.com/geerlingguy/docker-rockylinux8-ansible)
- [Ubuntu 22.04](https://github.com/geerlingguy/docker-ubuntu2204-ansible)

Note: Those are special images from [Jeff Geerling](https://github.com/geerlingguy), which are designed to test Ansible playbooks

Or, if you just want to build an environment, have the playbook run inside it, then be able to log in and observe the environment, run:

    molecule converge

And then, to log into the environment:

    molecule login
