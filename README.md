# HAProxy

This will configure a highly available HAProxy configuration.

## Requirements
### Tooling
- Ansible >= 2.9.10

# Directions for usage
This is currently being run as a playbook from a local workstation. 

## Steps 
1. Clone the repo onto the local workstation to run the playbook locally.
2. Modify the hosts file consisting of the public IPs and host variables of the target hosts.  
3. Modify the ssh.cfg file that designates the username, port and ssh connection information for the target host.
4. Modify the vars/main.yml file with the proper variables.
5. Run the script:
```
ansible-playbook -i hosts main.yml -vv
```
Optional:
Run the script against a specific host or host category in the host file
```
ansible-playbook -i hosts main.yml -vv -l <instance IP>
``` 