# ivansible.lin_docker

Install
[docker-ce](https://docs.docker.com/install/linux/docker-ce/ubuntu/#install-using-the-repository),
[docker-compose](https://docs.docker.com/compose/install/#install-compose),
[docker-machine](https://docs.docker.com/machine/install-machine/#install-machine-directly),
ansible docker bindings.


## Requirements

None


## Variables

Available variables are listed below, along with default values.

    docker_machine_release: latest
Docker-machine release to install. See new releases at
https://github.com/docker/machine/releases

    docker_compose_release: latest
Docker-compose release to install. See new releases at
https://github.com/docker/compose/releases

    docker_allow_reinstall: false
Allows to refresh already downloaded docker redistributables.

    docker_permit_user: false
True allows to add target user in the docker group.

    docker_hub_username: ""
    docker_hub_password: ""
Use non-empty values to login target user into docker hub. Only user
in the docker group (`docker_permit_user` is true) will be authenticated.

    docker_files_repo: ""
    docker_files_dir: ~/devel/docker
If current host belongs to the `permitted` group and the URL of Git repository
with user _docker files_ is defined and not empty, the repository will be
checked out in the given local directory.


## Tags

- `lin_docker_core` -- install docker core
- `lin_docker_ansible` -- install ansible docker bindings
- `lin_docker_compose` -- install docker-compose
- `lin_docker_machine` -- install docker-machine
- `lin_docker_user` -- give target user permissions for docker daemon
                       and login into docker hub
- `lin_docker_all` -- all tasks


## Dependencies

None


## Example Playbook

    - hosts: myhost
      roles:
        - role: ivansible.lin_docker


## License

MIT


## Author Information

Created in 2018-2020 by [IvanSible](https://github.com/ivansible)
