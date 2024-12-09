# Local Users and Groups

This is a very basic role for managing users and groups on a local Linux system

## Requirements

This role has no requirements beyond that of Ansible

## Role Variables

**localusergroup_users** - list of dictionaries containing the following

| field    | type   | required | default value | example          | description |
| -------- | ------ | -------- | ------------- | ---------------- | ----------- |
| username | string | true     |               |                  |             |
| state    | string | true     |               | present / absent |             |
| fname    | string | true     |               |                  |             |
| sname    | string | true     |               |                  |             |
| email    | string | true     |               |                  |             |
| password | string | true     |               |                  |             |
| sudo     | bool   | false    | false         | true             |             |
| groups   | list   | false    |               |                  |             |
| sshkeys  | list   | false    |               |                  |             |

**localusergroup_groups** - list of dictionaries containing the following

| field    | type   | required | default value | example          | description |
| -------- | ------ | -------- | ------------- | ---------------- | ----------- |
| name     | string | true     |               |                  |             |
| state    | string | true     |               | present / absent |             |


## Dependencies

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.


## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yml
localusergroup_users:
  - username: "username"  # This user will be added
    state: present
    fname: "user"
    sname: "name"
    email: user1@ansible.com
    password: 'set using openssl passwd -6'
    sudo: true
    groups:
      - "grouphere"
    sshkeys:
      - 'copypaste ssh key'
      - 'or use file read'
      - 'multiple_keys_can_be_used'

  - username: "another.user"  # This user will be removed
    state: absent

# Managing Groups
localusergroup_groups:
  - name: "infra"  # This group will be added
    state: present
```


### Generate password

Preferred method:
```bash
set using openssl passwd -6
```

Alternative method:
```bash
python3 -c 'import crypt,getpass;pw=getpass.getpass();print(crypt.crypt(pw) if (pw==getpass.getpass("Confirm: ")) else exit())'
```


## License

BSD

## Author Information


**Tristan Findley**

Find out more about me [here](https://tfindley.github.io).

If you're fan of my work and would like to show your support:

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/Z8Z016573P)
