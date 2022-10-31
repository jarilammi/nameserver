# Regional sustainability

Set at least one nameserver, one loadbalancer and one webserver for each regional area.

Whenever a client is able to reach a nameserver, it means that there is at least one loadbalancer or webserver available in that region.

If the network ever disconnects between the regions, there should still be a server available. If that outage lasts long enough, the local server will eventually be resolved correctly and the service restored even if the Network connectivity didn't.

## Running the Ansible playbook

Edit the [production](https://github.com/jarilammi/nameserver/blob/main/production) file to indicate the real IP addresses of the nameservers, loadbalancers and webservers. Alternatively, you may use the Fully Qualified Domain Names for the ansible_host variable.

Run the playbook with command:

```
% ansible-playbook -i production dns.yml
```

If you get multiple prompts for your ssh key password, present each NS/LB/FE server separately by commenting the other servers in the production file. After that it should work with all of them at the same time.
