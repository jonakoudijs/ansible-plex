[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE.md)

# Ansible Plex

Complete Plex installation with Ansible (includes SyncLounge and tls proxy).

## Variables

In general all of the available variables that can be set, can be found in the defaults of the roles. The most important variables to change are the domains of Plex and/or SyncLounge. Traefik uses these domains to request tls certificates via Let's Encrypt:
```
plex_domain: "plex.example.com"
synclounge_domain: "plex-sync.example.com"
```
When Plex is setup via Docker (the default) then the (data) volume must be set as well. Use the Docker style syntax, for example:
```
plex_docker_volumes:
  - "/home/plex/movies:/movies"
```

## Installation Method

The roles support two installation methods; Docker and Manual. By default the Docker method is used because it's the recommended way, especially for SyncLounge. To use the manual installation method for Plex and/or SyncLounge you will have to disable the Docker installation:
```
plex_docker: false
synclounge_docker: false
```
The manual installation will install all the software directly on the server (without containers). For SyncLounge this means it has to build SyncLounge via NPM which takes a long time (and sometimes times out).

## Development

To test it locally, [Vagrant](https://www.vagrantup.com/) can be used. A VM will be created locally and the `install.yml` playbook will be executed on it:
```
vagrant up
```

## License

[MIT license](LICENSE)
