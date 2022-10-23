# Running the Ansible playbook

Edit the production file to indicate the real IP addresses of the nameservers. Also edit the roles/ufw/vars/main.yml file if you use other hostnames than ns1 and ns2.

Run the playbook with command:

```
% ansible-playbook -i production dns.yml
```

If you get multiple prompts for your ssh key password, present each NS server separately by commenting the other servers in the production file. After that it should work with all of them at the same time.
