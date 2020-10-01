Postfix.SES
=========

Ansible role to configure Amazon SES within Postfix

Required Variables
----------------

```yaml
# SES host
postfix_ses_host: email-smtp.eu-central-1.amazonaws.com

# Port of SES host
postfix_ses_port: 587

# SES username to login
postfix_ses_username: my-username

# SES password to login
postfix_ses_password: my-complicated-password

# Postfix canonical name to map address
postfix_canonical_name: support@grandcruwijnen.nl
```

Default Variables
----------------
```yaml
# Packages to install to make SES work
postfix_ses_packages:
  - postfix
  - s-nail
  - libsasl2-modules

# Location of template file for /etc/postfix/main.cf
postfix_ses_postfix_template: "postfix.cf.j2"

# Location of template file for /etc/postfix/sender_canonical
postfix_ses_canonical_template: "sender_canonical.j2"

# Location of template file for /etc/postfix/sasl_passwd
postfix_ses_sasl_template: "sasl_passwd.j2"

# Location of where sasl_passwd should be written to
postfix_ses_sasl_passwd: "/etc/postfix/sasl_passwd"

# Location of where the ca-certificates certificate file is located
postfix_ses_ca_certificates: "/etc/ssl/certs/ca-certificates.crt"
```

Example Playbook
----------------

    - hosts: all
      roles:
         - { role: jketelaar.postfix-ses }

License
-------

MIT

TODO items
------------------
- Check if files already exist and have the right content
    - There is no need to recreate files (or even restart postfix) if there is no change
