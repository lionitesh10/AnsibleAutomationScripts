### To Check Syntax
$ ansible-playbook playbook.yml --syntax-check







### Ansible Vault:
It is an encyption to the playbook content. It uses AES 256 algorithm to encrypt the playbook.
Uses password or key to encrypt.

<br/>To Create a encrypted playbook.
[ansibleuser@ansible playbooks]$ ansible-vault create testvault.yml

<br/>
[ansibleuser@ansible playbooks]$ vi testvault.yml
<br/>
--- Encrypted Content
<br/>
To edit a encrypted playbook.
<br/>
[ansibleuser@ansible playbooks]$ ansible-vault edit testvault.yml

<br/>
To encrypt an existing playbook
<br/>
[ansibleuser@ansible playbooks]$ ansible-vault encrypt apacheinstallation.yml
<br/>
Encryption successful
<br/>
[ansibleuser@ansible playbooks]$ vi apacheinstallation.yml
<br/>
To decrypt an encrypted playbook.
<br/>
[ansibleuser@ansible playbooks]$ ansible-vault decrypt apacheinstallation.yml
<br/>
Vault password:
<br/>
Decryption successful

