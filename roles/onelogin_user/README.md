Role Name
=========

Configure Onelogin users and assign roles

Requirements
------------

- `onelogin_token` role imported

Role Variables
--------------

See default/main.yml

*input*

- onelogin_user_data: user data dictionary in the following format

```
user_data:
  user_email_base: tower.net
  user_password: r3dH@t254
  user_list:
  - username: app.dev
    department: application
  - username: app.qa
    department: application
  - username: app.ops
    department: application
  - username: platform.dev
    department: platform
  - username: platform.qa
    department: platform
  - username: platform.ops
    department: platform
```

- onelogin_user_role_id: role id to assign to the user

*output*

none

Dependencies
------------


Example Playbook
----------------


License
-------

BSD

Author Information
------------------

Marc Petrivelli mpetrive@redhat.com
