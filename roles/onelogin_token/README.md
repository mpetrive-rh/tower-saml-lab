Role Name
=========

onelogin token role to obtain oath2 token

Requirements
------------

- onelogin developer account
- API access setup at https://CUSTOMER_NAME.onelogin.com/api_credentials and client_id and client_secret recorded

Role Variables
--------------

*input*

- onelogin_token_client_id: client_id from onelogin API creds
- onelogin_token_client_secret: client_secret from onelogin API creds

*output*

- onelogin_token_access_token: access token to be used in future requests in header. `Authorization: bearer {{ onelogin_token_access_token }}`

- onelogin_base_url: base API url

Dependencies
------------



Example Playbook
----------------

- name: get a onelogin oath2 token and base vars
  import_role:
    name: onelogin_token
  vars:
    onelogin_token_client_id: "{{ onelogin_client_id }}"
    onelogin_token_client_secret: "{{ onelogin_client_secret }}"

License
-------

BSD

Author Information
------------------

Marc Petrivelli mpetrive@redhat.com
