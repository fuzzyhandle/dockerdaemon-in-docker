FROM centos:latest
ENV container docker

RUN yum -y update
RUN yum -y install systemd 
RUN yum -y install docker 
RUN yum -y install e2fsprogs 
RUN yum -y install coreutils
RUN yum -y install iptables
RUN yum clean all

ADD init.sh /init.sh
RUN chmod a+x /init.sh
ADD loopdevice.service /usr/lib/systemd/system/loopdevice.service
RUN sed -i "s/^Wants=.*/Wants=loopdevice.service/g" /usr/lib/systemd/system/docker.service

RUN systemctl enable docker
EXPOSE 22

VOLUME ["/sys/fs/cgroup"]
CMD ["/usr/sbin/init"] 
