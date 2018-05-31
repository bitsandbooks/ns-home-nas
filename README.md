ns-home-nas
=========

This role sets up my home nas server.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

There's one major variable, `sudo_users`, which can have as many users as you'd like. Each user has four properties: `username`, `upasswd`, `passwd` and `uid`, each of which correspond to a property of each user.

Example:

    sudo_users:
      - username: bob
        upasswd: bobs_password
        passwd: $6$bobs_salt$V4zX9pmG52IUH1y6hjLu8ji9bY3ABpumRnGcped5iFaQFVQ.3gmOS8CySNSIFV2SLdNQ2wbLwux9EcYusE1AA0
        uid: 1001
      - username: jane
        upasswd: janes_password
        passwd: $6$janes_salt$KZRrF9P7aQYGvq1m8cB.Q8GFCcB5RTVE8LNEQN4vQ4hsM1qM6nxl8rVKhq8lM5ybO0nlpeRSy2Lo1NVhtyTaU0
        uid: 1002

**Security note:** Don't change the values in `defaults/main.yml` and don't put them in `vars`, either! Instead, put them in your "secrets" file (e.g., `/srv/ansible/group_vars/all/secrets.yml`) and/or encrypt them using `ansible-vault`.

Dependencies
------------

No known dependencies

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: bitsandbooks.ns-home-nas }

License
-------

BSD

Author Information
------------------

By [Rob Dumas](https://github.com/bitsandbooks)
