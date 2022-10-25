## Running the Ansible playbook

Edit the production file to indicate either the real IP addresses or Fully Qualified Domain Names of the nameservers and loadbalancers.

Run the playbook with command:

```
% ansible-playbook -i production dns.yml
```

If you get multiple prompts for your ssh key password, present each NS server separately by commenting the other servers in the production file. After that it should work with all of them at the same time.
