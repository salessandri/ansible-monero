# Monero

This role sets up a [Monero](https://www.getmonero.org/) full node using a [docker container](https://hub.docker.com/repository/docker/salessandri/monerod).

## Requirements

This role relies on `docker` being available on the host and the [`community.general.docker_container` module](https://docs.ansible.com/ansible/2.10/collections/community/general/docker_container_module.html) in ansible.

[`geerlingguy.docker` role](https://galaxy.ansible.com/geerlingguy/docker) can be used to setup docker.
For the `docker_container` python module, [`geerlingguy.pip` role](https://galaxy.ansible.com/geerlingguy/pip) can be used to install Python's [`docker` package](https://pypi.org/project/docker/).

## Role Variables

 - **`monero__version`** (optional, default: _0.18.1.0_): Image version tag to use.
 - **`monero__container_name`** (optional, default: _monerod-node_): Name to use for the container created by the role.
 - **`monero__data_dir`** (optional, default _/var/monero/_): Folder to use for persistent files.
 - **`monero__config_file`** (optional, default: _files/monerod.conf_): Config file for the service.
 A default one is provided by the role but you are encouraged to provide your own.
 - **`monero__p2p_port`** (optional, default: _18080_): Port on which the peer to peer port will be exposed on the host machine.
 - **`monero__rpc_port`** (optional, default: _18081_): Port on which the rpc port will be exposed on the host machine.

## Example Playbook

The following would be a fairly common role usage example:

```yaml
- host: monerod.my-domain.com
  roles:
    - role: salessandri.monero
```

## License

MIT

## Author Information

This role was created in 2021 by [Santiago Alessandri](https://rambling-ideas.salessandri.name).
