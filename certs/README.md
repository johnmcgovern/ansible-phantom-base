# Ansible-Phantom-Base ./certs/

To upload custom SSL certs to install with Phantom for the Web UI:

1. In group_vars/all set use_custom_ssl_certs to "true"

2. Place your public key (PEM format) in certs/httpd_cert.crt (include intermediate chain after the public key if available).

3. Place your private key (PEM format) in certs/httpd_cert.key.

4. This project will upload the certs to their default locations and restart the Phantom nginx server.