# CI Server with Ansible

Provision CI server with Ansible including

 * jks
 * jenkins
 * jdk
 * docker
 * git
 * ansible
 * terraform
 * aws cli
 * azure cli

## Required Parameters (provide via vault)

 * `jks_password` - keystore password for jenkins
 * `jenkins_admin_username` - admin username
 * `jenkins_admin_password` - admin password
 * `jenkins_global_secrets` - list of items as show below

```
jenkins_global_secrets:
  - name: test1-secret
    description: this is test 1
    text: test1-secret-value
```

## Expected Parameters (via variables file)

 * `ci_user` - user for ci (jenkins)
 * `jks_location` - location of the java keystore
 * `jks_subject` - subject details for certificate
 * `jks_alias`: - alias for keystore
 * `git_user_name` - username for git config
 * `git_user_email` - email for git conig
 * `terraform_version` - version of terraform

## Testing

Credit: Tested with vagrant image from [@geerlingguy's Ansible for Devops](https://github.com/geerlingguy/ansible-for-devops)

### Initial Install
```
ansible-galaxy install -r requirements.yml
vagrant up
```

### Reapply provisioning
```
vagrant provision
```
