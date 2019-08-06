Ansible Tower SAML integration with Onelogin Identity Provider
=========

[Repository link](https://gitlab.consulting.redhat.com/automation_practice/tower-saml-lab)

This builds on the excellent Ansible blog post [Using SAML with Ansible Tower](https://www.ansible.com/blog/using-saml-with-red-hat-ansible-tower) by Chris Meyers of Ansible Engineering fame.  The playbooks and roles provided in this repo automates the configuration outline in the aforementioned blog post and provides additional configuration of Ansible Tower and Onelogin identity provider (SAML)

This content can help consultants understand how Ansible Tower SAML integration is configured, basic Tower SAML RBAC and building out an Onelogin SAML application


Requirements
------------

- Ansible Tower
 - Fully installed and licensed
 - Exposed on a Public IP/hostname
 - Base url set to public IP/hostname (see [System configuration](https://docs.ansible.com/ansible-tower/latest/html/administration/configure_tower_in_tower.html#system) )

- Onelogin
 - Developer account with company/customer OneLogin domain created (ie https://customer1-dev.onelogin.com)
 - API Access credentials for admin user created (https://customer1-dev.onelogin.com/api_credentials) with `client_id` and `client_secret` noted


Workflow
--------------

1. get oath2 access onelogin token

1. determine default Onelogin role to use for Tower application

1. get current Tower SAML configuration (ie Tower ACS url)

1. create and configure Onelogin SAML 2.0 application

1. create Onelogin users and assigned default role, password

1. configure Tower SAML integration


Usage
---------------------

1. Clone this repository

   ```ssh://git@gitlab.consulting.redhat.com:2222/automation_practice/tower-saml-lab.git```

1. Copy `private-vars-template.yml` to `private-vars.yml`

   ```cp private-vars-template.yml private-vars.yml```

1. Update `private-vars.yml` with the information for your Ansible Tower and Onelogin environment.  All values with `<<description>>` should be updated

1. Run the configuration playbook to configure Ansible Tower and Onelogin

   ```ansible-playbook onelogin.yml```

1. Log in to Ansible Tower using the SSO button

Details
------------------------

- The `private-vars-template.yml` has the users (`user_data.user_list`) that will be created in Onelogin.  This list can be adjusted accordingly

- The `department` field in the user list is used for RBAC mappings.  Each unique department will map to Ansible Tower organizations.  The department is exposed in the SAML assertion sent to Ansible Tower.

- The Ansible Tower SAML RBAC configuration in the `tower_saml` role is currently hard coded to use the department.

- The `Default` role in Onelogin is given access to the newly create Onelogin application.  All users are given the default role


License
-------

BSD

Author Information
------------------

Marc Petrivelli mpetrive@redhat.com
