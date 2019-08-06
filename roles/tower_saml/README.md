Role Name
=========

Configure and obtain Tower SAML configuration.  Generates certificate/key for use in SAML configuration.  Provides for information gather only

Requirements
------------

- `onelogin_token` role imported

Role Variables
--------------

See default/main.yml

*input*

- tower_saml_host: tower API location
- tower_saml_username: tower API user
- tower_saml_password: tower API password
- tower_saml_vars_only: indicated whether Tower SAML configuration should be read vs written. Default: false

if `tower_saml_vars_only == true`

- tower_saml_audience: SAML audience name/ Tower entity ID
- tower_saml_issuer_metadata_url: onelogin issuer URL
- tower_saml_endpoint_url: onelogin SAML2.0 endpoint
- tower_saml_cert: onelogin SAML2.0 certificate in string format

*output*

- tower_saml_callback_url: Tower ACS URL for SSO callback
- tower_saml_metadata_url: Tower ACS metadata URL


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
