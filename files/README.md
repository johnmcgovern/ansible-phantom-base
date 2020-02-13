# Ansible-Phantom-Base ./files/

To the best of my knowledge Splunk Phantom does not allow unauthenticated wgets so we have to do things differently than in ansible-splunk-base where we can pull down the .tgz directly.

To use this project, first download the "unprivileged" TGZ installer from https://my.phantom.us/downloads/. Then place the downloaded .tgz in ./files/ so that ansible can upload it to the remote host.

The version strings set in ./group_vars/all should match the filename and checksum (SHA256) of the .tgz that you downloaded.

