Role : ansible-role-vault-pkiremove
===================================

Unconfigure Vault's PKI
* Disable PKI engine
* Disable intermediate PKI engine

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
```

Dependencies
------------

Requires elevated root privileges

Example Playbook
----------------

```
---

- name: Unconfigure Vault PKI
  hosts: vault
  gather_facts: no

  roles:

    - name: Unconfigure PKI
      role: ansible-role-vault-pkiremove
      tags:
        - 'never'
        - 'remove'
```

License
-------

MIT License

Author Information
------------------

Adam Goldsmith

