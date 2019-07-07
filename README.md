# ansible

## Usage
`$ ansible-playbook -i <inventory.yml> <playbook.yml>` 

`$ ansible-playbook -i <inventory.yml> <playbook.yml> --tags <tag>`

## Example
command

`$ ansible-playbook -i inventory.yml playbook.yml --tags setup/amazon_linux2`


inventory.yml
```
[webservers]
12.34.56.78 ansible_user=ec2-user

[webservers:vars]
Name_tag=web
```

playbook.yml
```
- hosts: webservers
  roles:
    - { role: setup/amazon_linux2, tags: setup/amazon_linux2 }
```

