prometheus_docker_deploy
=========
This role creates the prometheus container set as requested by the ActiveBC DevOps team :)


Role Variables
--------------
You must provide this role with the set of variables (see the example below):
``` yaml
prometheus_containers:
  - container_name: prom1
    version: v2.40.1
    exposed_port: 9090
    retention_time: 1d
  - container_name: prom2
    version: v2.39.2
    exposed_port: 9091
    retention_time: 15d
  - container_name: prom3
    version: v2.39.2
    exposed_port: 9092
    retention_time: 30d
```

Dependencies
------------

Install ansible-galaxy community.docker collection if it doesn't exist
```
ansible-galaxy collection install community.docker
```

Example Playbook
----------------

The role usage example: 
```yaml
    - hosts: servers
      roles:
         - role: prometheus_docker_deploy
```
