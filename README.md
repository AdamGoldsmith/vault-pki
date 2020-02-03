# Certificate Generation

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Use Hashicorp Vault to generate TLS certificates

See [hashicorp documentation](https://learn.hashicorp.com/vault/secrets-management/sm-pki-engine#) for details

__To configure PKI__

`ansible-playbook playbooks/pki.yml`

__To unconfigure__

`ansible-playbook playbooks/pki.yml --tags 'remove'`

>__Note__: Highly recommended to have deployed Vault + Consul cluster using the Ansible playbooks at this [repository](https://github.com/AdamGoldsmith/consul-vault), or at least peruse for better understanding

