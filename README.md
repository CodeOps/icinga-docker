# Icinga Docker Containers

Various Docker Containers used for testing.

> **Note**
>
> Constant work-in-progress, not yet finished!

## Docker Installation

https://docs.docker.com/installation

### Debian Jessie

    $ sudo apt-get update
    $ sudo apt-get install docker.io
    $ sudo ln -sf /usr/bin/docker.io /usr/local/bin/docker
    $ sudo sed -i '$acomplete -F _docker docker' /etc/bash_completion.d/docker.io


## Containers

### icinga2x

#### centos6

> **TODO**
>
> Install DB backend, GUIs, configure graphite

    $ cd icinga2x/centos6 && sudo ./run

Repositories:

  Repository		| Url
  ----------------------|----------------------
  EPEL			| https://fedoraproject.org/wiki/EPEL
  Icinga Snapshots	| http://packages.icinga.org/epel/

Software:

  Name			| Packages
  ----------------------|----------------------
  base			| wget vim mailx
  icinga2		| icinga2 icinga2-bin icinga2-common icinga2-doc icinga2-ido-mysql
  httpd			| httpd
  graphite		| python-whisper python-carbon graphite-web

Configuration:

  Name			| Location
  ----------------------|----------------------
  icinga2		| /etc/icinga2/conf.d


