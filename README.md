# DevOpsLabs for Ansible

## How to use these Labs
1. Install Oracle Virtual Box:  https://www.virtualbox.org/

2. Install Vagrant: https://www.vagrantup.com/downloads.html

3. Start the vagrant instance.
``` shell
vagrant up
```

4. SSH into the ansible-control virtual machine.
``` shell
vagrant ssh ansible-control
```

5. Install ansible(latest version, otherwise galaxy roles won't work)
``` shell
sudo apt isntall ansible -y
```

6. Copy hosts for ansible-control
``` shell
cp /vagrant/hosts_file /etc/hosts
```

7. Generate ssh-key on ansible-control
``` shell
ssh-keygen
```

8. Copy ssh-key to all hosts
ssh-copy-id {hostname1} && ssh-copy-id {hostname2} etc ...

9. Install simplejson
``` shell
ansible all -i hosts -m command -a 'sudo apt install -y python-simplejson'
```

10. Install galaxy roles if needed
``` shell
ansible-galaxy role install geerlingguy.docker
```

11. Execute single playbooks
``` shell
ansible-playbook -i inventories/dev install_docker.yml
```

12. Run all playbooks
``` shell
ansible-playbook -i inventories/dev playbook.yml
```

NOTE: Playbooks outside roles should should have 'tasks', 'hosts' and 'become'
Use ansible all -i inventories/dev -m debug -a "msg='{{ welcome_msg }}'" to check set env. vars in groups_vars