# Introduction To Ansible
Ansible is an open source automated configuration management, deployment tool written on python. It is an automated infrastructure as Code (IAC) tool. It turns your code into an infrastructure. It works on push mechanism which means that it will automatically push the updates to the connected hosts as triggered. No Pull mechanism server do not have to ask for updates to the connected nodes.
<br/>
It is an agentless tool i.e no need to install anything on hosts (connected nodes) . It uses an YAML (Yet Another Markup Language ) to configure infrastructures. It communicates with hosts directly through SSH (Secure Shell Protocol ) which runs on port 22.
<br/>

The major topics on ansible are: 
<br/>
1. Ansible Inventory: 
<br/>
Ansible Inventory is the database of the hosts. It contains the IP Addresses of host nodes. Groups is also defined in this database. Its location is /etc/ansible/hosts file. You can edit /etc/ansible/hosts file to add the hosts IP Addresses. Such as : <br/>
192.168.64.1 --> Single IP address
<br/>
192.168.64.2 
<br/>
[developers] --> Represent Group
<br/>
192.168.64.1
<br/>
192.168.64.2

<br/>
2. Ansible.cfg:
    It is the configuration file for ansible. It contains all the configurations for ansible to run.
    It is located in /etc/ansible/ansible.cfg file.
<br/>
3. Ansible Playbook:
<br/>
Ansible playbook is the yaml file where the automation script is written in yaml format. It is written using the collection of modules of ansible. It can be placed anywhere in the server.

### Ansible Ad hoc Commands
Ansible Ad hoc commands are the quick temporary commands that can execute a task in the connected nodes. It is used to do a quick fix or a quick command. It doesnot provide IDEMPOTENCY. Can be used to do only single work.
<br/>
$ ansible all -a "touch file1"
<br/>
all --> Represents all the nodes in hosts file
<br/>
-a ---> Represents argument
<br/>
$ ansible developers -ba "useradd ram"
<br/>
developers --> Represents IPAddress under developers group 
<br>
-b ---> Represents to run command as a sudo user

<br/>
$ ansible developers[0] -ba "useradd ram"
<br/>
developers[0] --> Represents first IPAddress under developers group 
<br/>
-b ---> Represents to run command as a sudo user


### To Check Syntax
$ ansible-playbook playbook.yml --syntax-check

### DRY RUN 
$ ansible-playbook playbook.yml --check






### Ansible Vault:
It is an encyption to the playbook content. It uses AES 256 algorithm to encrypt the playbook.
Uses password or key to encrypt.
<br/>
<br/>
To Create a encrypted playbook.
<br/>
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

