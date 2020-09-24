# HAProxy

This will configure a highly available HAProxy service
consisting of a master and slave.

HAProxy will handle load-balancing on layer 7. 
keepalived runs on both the active and passive servers and
works by monitoring the heartbeat of the active server at periodic intervals. 


## Requirements
### Tooling
- Ansible >= 2.9.10

# Directions for usage
This is currently being run as a playbook from a local workstation. 

## Steps 
1. Clone the repo onto the local workstation to run the playbook locally.
2. Modify the hosts file consisting of the public IPs and host variables of the target hosts.  
3. Modify the vars/main.yml file with the proper variables.
4. Run the script:
```
ansible-playbook -i hosts main.yml -vv
```
Optional:
Run the script against a specific host or host category in the host file
```
ansible-playbook -i hosts main.yml -vv -l <instance IP or host category>
``` 

## Notes
- The haproxy.cfg file must be modified to suit the user's needs.
- notify_master.sh is written for aws using aws cli. This should be converted to bash or something platform agnostic. 