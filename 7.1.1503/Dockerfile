FROM       centos:7.1.1503
MAINTAINER lnterface "https://github.com/lnterface/centos-ssh"

RUN yum update && \
    yum install -y openssh-server && \
    yum clean all
    
RUN mkdir /var/run/sshd

RUN echo 'root:toor' |chpasswd

RUN sed -ri 's/^PermitRootLogin\s+.*/PermitRootLogin yes/' /etc/ssh/sshd_config
RUN sed -ri 's/UsePAM yes/#UsePAM yes/g' /etc/ssh/sshd_config

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]