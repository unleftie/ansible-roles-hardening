# Ansible Role for hardening

[![CI](https://github.com/unleftie/ansible-roles-hardening/actions/workflows/ci.yml/badge.svg)](https://github.com/unleftie/ansible-roles-hardening/actions/workflows/ci.yml)
[![OpenSSF Scorecard](https://api.securityscorecards.dev/projects/github.com/unleftie/ansible-roles-hardening/badge)](https://securityscorecards.dev/viewer/?uri=github.com/unleftie/ansible-roles-hardening)

Thin wrapper role that applies [`devsec.hardening.os_hardening`](https://github.com/dev-sec/ansible-collection-hardening/tree/master/roles/os_hardening)
and [`devsec.hardening.ssh_hardening`](https://github.com/dev-sec/ansible-collection-hardening/tree/master/roles/ssh_hardening) from the upstream
[dev-sec.hardening](https://galaxy.ansible.com/ui/repo/published/devsec/hardening/) collection. Override variables live in [defaults/main.yml](defaults/main.yml).

## Compatibility

| Platform | Version |
| -------- | ------- |
| debian   | 12      |

## SSH Warning

This role disables root-login on the target server! Please make sure you have another user with su or sudo permissions that can login into the server.

## Dependencies

- [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) (v2.14+)
- [Molecule](https://molecule.readthedocs.io/en/latest/installation.html) + (v4.0.4+) + [docker plugin](https://github.com/ansible-community/molecule-plugins) (for local testing)
- [Docker](https://docs.docker.com/get-docker/) (for local testing)

## Local Testing

```sh
git clone https://github.com/unleftie/ansible-roles-hardening.git
cd ansible-roles-hardening
ansible-galaxy install -r requirements.yml
molecule test
```

## Installation

```sh
ansible-galaxy install -r requirements.yml
```

Example [playbook](main.yml)

## 📝 License

This project is licensed under the [Apache License](LICENSE).
