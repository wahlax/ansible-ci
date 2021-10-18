# CI Server with Ansible

Provision CI server with Ansible including

 * jenkins
 * jdk
 * docker
 * git


## Testing

### Install roles from git
```
ansible-galaxy install -r requirements.yml
```

Credit: Tested with vagrant image from [@geerlingguy's Ansible for Devops](https://github.com/geerlingguy/ansible-for-devops)

### Initial Install
```
vagrant up
```

### Reapply provisioning
```
vagrant provision
```
