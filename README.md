# Icinga Docker Containers

Various Docker Containers used for testing.

> **Note**
>
> Constant work-in-progress, not yet finished!

## Docker Installation

https://docs.docker.com/installation

### Fedora 20

    # yum install docker-io


### Debian Jessie

    # apt-get update
    # apt-get install docker.io
    # ln -sf /usr/bin/docker.io /usr/local/bin/docker
    # sed -i '$acomplete -F _docker docker' /etc/bash_completion.d/docker.io


## Containers

### icinga2x

#### centos6

Requires an import of the [centos docker images](http://wiki.centos.org/Cloud/Docker):

    # docker pull centos
    # docker images centos

> **TODO**
>
> Install DB backend, GUIs, configure graphite

Navigate into the directory with the `Dockerfile` file and run
the docker image using the provided `run` script:

    # cd icinga2x/centos6 && ./run

Repositories:

  Repository		    | Url
  ----------------------|----------------------
  EPEL			        | https://fedoraproject.org/wiki/EPEL
  Icinga Snapshots	    | http://packages.icinga.org/epel/

Software:

  Name			        | Packages
  ----------------------|----------------------
  base			        | wget vim mailx
  icinga2		        | icinga2 icinga2-bin icinga2-common icinga2-doc icinga2-ido-mysql
  httpd			        | httpd
  graphite		        | python-whisper python-carbon graphite-web

Configuration:

  Name			        | Location
  ----------------------|----------------------
  icinga2		        | /etc/icinga2/conf.d


