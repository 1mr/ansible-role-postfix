Postfix
=======

This role helps to install and configure postfix.

Requirements
------------

This role requires ansible 1.4 or higher.

Role Variables
--------------

The variables that can be passed to this role and a brief description about them are as follows:

Obligatory variables:

    postfix_aliases:
      root:
        alias: admin@example.com, duty@example.com
      www-data:
        alias: webdev@example.com

Optional variables:

    postfix_myhostname: app1.example.com
    postfix_mydomain: example.com
    postfix_myorigin: $mydomain

    postfix_mynetworks:
      - 127.0.0.0/8
      - 192.168.0.0/24

    postfix_inet_interfaces:
      - 127.0.0.1
      - 192.168.0.1

    postfix_message_size_limit: 102400000

    postfix_relayhost: relay.example.com
    postfix_relayhost_port: 587
    postfix_relayhost_user: user
    postfix_relayhost_password: password

    postfix_relay_domains:
      - example.com
      - example.net

    postfix_smtp_tls_cafile: /etc/ssl/certs/ca-certificates.crt
    postfix_smtp_sasl_auth_enable: yes
    postfix_smtp_sasl_security_options: noanonymous
    postfix_smtp_sasl_password_maps: /etc/postfix/sasl/passwd
    postfix_smtp_use_tls: yes
    postfix_smtp_tls_security_level: encrypt
    postfix_smtp_tls_note_starttls_offer: yes

Dependencies
------------

Roles:
- opendkim (optional)

Example Playbook
----------------

    - hosts: servers
      roles:
        - { role: 1mr.postfix, tags: postfix }

License
-------

BSD

Author Information
------------------

Created by Stas Stavnichuk
