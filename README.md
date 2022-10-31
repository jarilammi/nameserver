# Regional sustainability

Whenever a client is able to reach a nameserver, it means that there is at least one loadbalancer or webserver available in that region.

If the network disconnects between the regions, there should still be a server available. If that outage lasts long enough, the local server will be eventually be resolved correctly and the service restored even if the Network connectivity didn't.

## Running the Ansible playbook

Edit the production file to indicate either the real IP addresses or Fully Qualified Domain Names of the nameservers and loadbalancers. Also edit the IP addresses on lines 22 and 23 in the roles/bind9/templates/cq.fi.j2 template.

Run the playbook with command:

```
% ansible-playbook -i production dns.yml
```

If you get multiple prompts for your ssh key password, present each NS/LB/FE server separately by commenting the other servers in the production file. After that it should work with all of them at the same time.
