### To Check Syntax
$ ansible-playbook playbook.yml --syntax-check







### Ansible Vault:
It is an encyption to the playbook content. It uses AES 256 algorithm to encrypt the playbook.
Uses password or key to encrypt.

TO Create a encrypted playbook.
[ansibleuser@ansible playbooks]$ ansible-vault create testvault.yml
New Vault password:
Confirm New Vault password:


[ansibleuser@ansible playbooks]$ vi testvault.yml
--- Encrypted Content

To edit a encrypted playbook.
[ansibleuser@ansible playbooks]$ ansible-vault edit testvault.yml
Vault password:

To encrypt an existing playbook
[ansibleuser@ansible playbooks]$ ansible-vault encrypt apacheinstallation.yml
New Vault password:
Confirm New Vault password:
Encryption successful
[ansibleuser@ansible playbooks]$ vi apacheinstallation.yml

To decrypt an encrypted playbook.
[ansibleuser@ansible playbooks]$ ansible-vault decrypt apacheinstallation.yml
Vault password:
Decryption successful

