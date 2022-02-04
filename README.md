# ansible-deploy-registry

Deploy a docker registry v2 using podman.

Tested on RHEL8.

# Usage
```shell
git clone https://github.com/gauthiersiri/ansible-deploy-registry
```
Edit :
- `group_vars/main.yaml`
- `hosts`

```shell
sudo ansible-playbook deploy_registry.yaml
```

# Vars

| Variable        | Required? | Description                                                        |
|-----------------|-----------|--------------------------------------------------------------------|
| hostname        | yes       | Used to generate the certificate and test connectivity             |
| registry.image  | yes       | Docker image to use run the registry                               |
| registry.port   | yes       | port on which the registry is running                              |
| users           | yes       | List of users to create on the registry. Need at least one.        |
| docker_io.user  | no        | username to log on docker.io registry (and avoid pull rate issue)  |
| docker_io.token | no        | token to log on docker.io registry (and avoid pull rate issue)     |

# Start/stop/restart/status of the registry

```shell
sudo systemctl start|stop|restart|status local-registry
```