# ansible-role-user

This role configures user.

## Requirements

None.

## Role Variables

variable           | required | default | choice  | comment
------------------ | -------- | ------- | ------- | -------------------
name               | yes      |         |         | name
uid                | no       |         |         | uid
group              | yes      |         |         | primary group
groups             | no       |         |         | groups user belongs to, must be defined by comma-delimited list of groups.
password           | yes      |         |         | password
home               | no       |         |         | home directory
ssh_key            | no       |         |         | ssh public key, key file must be stored in *`files`* directory of this role.
sudo               | no       |         | yes, no | sudo permission
sudo_need_password | no       |         | yes, no | sudo password setting

## Dependencies

None.

## Example Playbook

```yml
- hosts: servers
  roles:
    - user
```

*Inside `vars/main.yml`*:  
Variables must be defined by dictionary.
```yml
user:
  tamandu:
    group: tamandu
    groups: admins,developers
    password: password
    uid: 501
    ssh_key: tamandu_id_rsa.pub
    sudo: yes
    sudo_need_password: yes
```

## License

MIT

## Author Information
