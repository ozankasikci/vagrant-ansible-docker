To start: simply run `vagrant-up-example` shell file. This inits vagrant with some environment variables.

Vagrant provisions a centos/7 instance and installs docker within it.

Vagrant ansible handles ansible installation within VM, the environment variables gets passed from shell file to vagrant, and from vagrant to ansible. 

`database` playbook starts `install-docker-py` and `init-database` roles. `init-database` role uses `docker_container` ansible module to fire up a mariadb instance.

In short, Vagrant provisions a centos VM, passes variables to ansible, ansible uses docker module to fetch and start specified mariadb version with the given credentials within the VM.
