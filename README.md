# env

An experiment in creating a template portable development environment.

To bootstrap:

```
git submodule add https://github.com/drobbins/env.git env
git submodule init && git submodule update
cd env
vagrant up
```

Modify `replicator.yml` and `Vagrantfile` as necessary (e.g. open ports).

## Windows Notes

The Ansible provisioner cannot be run on Windows, since Ansible does not support Windows control machines. So a few more steps are necessary:

```
vagrant ssh
sudo yum install -y http://mirror.cc.columbia.edu/pub/linux/epel/6/i386/epel-release-6-8.noarch.rpm
sudo yum install -y ansible
cd /vagrant
su
echo 127.0.0.1 > /etc/ansible/hosts
ansible-playbook replicator.yml --connection=local
```
