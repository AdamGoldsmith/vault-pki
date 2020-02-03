Role : ansible-role-vault-pki
=============================

Configure Vault's PKI
* Create PKI policy
* Enable PKI engine
* Tune PKI engine
* Generate CA root certificate
* Configure CA & CRL URLs
* Enable intermediate PKI engine
* Tune intermediate PKI engine
* Generate intermediate CSR
* Sign intermediate CSR
* Import intermediate certificate into Vault
* Create domain role
* Request certificate bundle

Currently tested on these Operating Systems
* Oracle Linux/RHEL/CentOS
* Debian/Stretch64

Requirements
------------

* Ansible 2.5 or higher

Role Variables
--------------

defaults/main.yml
```
vault_admintokenfile: "~/.hashicorp_admin_token.json"       # Local file storing admin token
vault_addr: "10.1.42.10"                                    # Vault listener address
vault_port: "8200"                                          # Vault listener port
pki_max_lease_ttl: "87600h"                                 # PKI engine max lease TTL
pki_int_max_lease_ttl: "43800h"                             # Intermediate PKI engine max lease TTL
common_name: "common.com"                                   # Domain name for issuing certificates
ca_ttl: "87600h"                                            # Root CA cert TTL
role_max_ttl: "720h"                                        # Domain role max TTL
sub_domain_name: "test"                                     # Sub domain name (test.common.com)
sub_domain_ttl: "24h"                                       # Sub domain TTL
```

Dependencies
------------

Requires elevated root privileges

Example Playbook
----------------

```
---

- name: Configure Vault PKI
  hosts: vault
  gather_facts: no

  roles:

    - name: Configure PKI
      role: ansible-role-vault-pki
      tags:
        - 'pki'
```

License
-------

MIT License

Author Information
------------------

Adam Goldsmith

