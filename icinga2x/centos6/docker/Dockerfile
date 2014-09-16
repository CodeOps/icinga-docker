FROM centos:centos6
RUN yum -y install wget vim mailx
# REPO EPEL
RUN rpm --import https://fedoraproject.org/static/0608B895.txt
RUN wget http://mirror.de.leaseweb.net/epel/6/i386/epel-release-6-8.noarch.rpm
RUN rpm -i epel-release-6-8.noarch.rpm
# REPO ICINGA
RUN rpm --import http://packages.icinga.org/icinga.key
RUN wget http://packages.icinga.org/epel/ICINGA-snapshot.repo -O /etc/yum.repos.d/ICINGA-snapshot.repo
# INSTALL YUM
RUN yum makecache
RUN yum -y install icinga2 icinga2-bin icinga2-common icinga2-doc icinga2-ido-mysql
RUN yum -y install httpd
RUN yum -y install python-whisper python-carbon graphite-web
WORKDIR /home/icinga
USER icinga
ENV HOME /home/icinga
# FIX PERMISSIONS
RUN chown -R icinga:icinga /etc/icinga2/conf.d
# RUN DAEMONS
RUN service icinga2 restart
RUN service httpd restart
RUN service carbon-cache restart
