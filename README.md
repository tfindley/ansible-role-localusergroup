Role Name
=========

A brief description of the role goes here.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      become: yes
      gather_facts: true
      roles:
        - role: '/home/tristan/ansible/roles_vss/users'
      vars:
        users_present:
        - {username: user1,  sudo: True,     enabled: True,    fname: User,     sname: One,     email: user1@ansible.com,         password: EncryptedPasswordUser1, rsa: "https://github.com/user1.keys" }
        - {username: user2,  sudo: True,     enabled: True,    fname: User,     sname: Two,     email: user2@ansible.com,         password: EncryptedPasswordUser2, rsa: "ssh-rsa enteryourrpublickeystringhere user2@usersmachine.local" }
        - {username: user3,  sudo: True,     enabled: False,   fname: User,     sname: Three,   email: user3@ansible.com,         password: EncryptedPasswordUser3, rsa: }
        - {username: user4,  sudo: False,    enabled: True,    fname: User,     sname: Four,    email: user4@ansible.com,         password: EncryptedPasswordUser4, rsa: "user2_id_rsa.pub"}

        users_absent: 
        - "user5"
        - "user6"

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
