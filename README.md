# CI Server with Ansible

Provision CI server with Ansible including

 * jenkins
 * jdk
 * docker
 * git
 * ansible
 * terraform
 * aws cli
 * azure cli

## Required Parameters (provide via vault)

 * `jenkins_admin_username` - admin username
 * `jenkins_admin_password` - admin password
 * `jenkins_global_secrets` - list of items as show below

```
jenkins_global_secrets:
  - name: test1-secret
    description: this is test 1
    text: test1-secret-value
```

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
