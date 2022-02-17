# my-development-env

### Usage
1. create `.secret/local.yaml` like below
```yaml
ansible_become_pass: <password for sudo>
username: <git user.name>
useremail: <git user.email>
```

2. Run
```shell
ansible-playbook -i local playbook.yaml --extra-vars="@.secret/local.yaml"
```
