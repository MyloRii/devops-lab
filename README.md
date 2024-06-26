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

5. Install ansible
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
``` shell
ssh-copy-id {hostname}
```