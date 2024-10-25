# Users and Groups

A brief description of the role goes here.

## Requirements

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

## Role Variables

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

## Dependencies

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.


## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yml
- hosts: servers
  become: yes
  gather_facts: true
  roles:
    - role: 'usersandgroups'
  vars:

# Adding a user
  - username: "username"
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

# Removing a user
  - username: "another.user"
    state: absent

# Managing Groups
usersandgroups_groups:
  - name: "dcinfra"
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

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
