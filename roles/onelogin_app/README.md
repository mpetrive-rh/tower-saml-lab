Role Name
=========

Configure a Onelogin application

Requirements
------------

- `onelogin_token` role imported

Role Variables
--------------

See default/main.yml

*input*

- onelogin_app_name: Onelogin application name
- onelogin_app_description: Onelogin application description
- onelogin_app_saml_consumer_url: Tower ACS consumer URL
- onelogin_app_saml_recipient_url: Tower ACS consumer URL
- onelogin_app_saml_audience: SAML2.0 audience

*output*

- onelogin_app_certificate: Onelogin application certificate (full)
- onelogin_app_certificate_str: Onelogin application certificate (string)
- onelogin_app_acs_url: Onelogin SAML2.0 endpoint
- onelogin_app_issuer_url: Onelogin issuer URL

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
