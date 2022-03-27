#ターゲットノードのDcokerfile
FROM ubuntu:20.04

# install ssh server
RUN apt-get update
RUN apt-get install openssh-server -y

# create Public key
RUN ssh-keygen -f /etc/ssh/ssh_host_rsa_key -N '' -t rsa -y
RUN ssh-keygen -f /etc/ssh/ssh_host_ecdsa_key -N '' -t ecdsa -y

# set to login as root for ubuntu
RUN sed -ri 's/^#PermitEmptyPasswords no/PermitEmptyPasswords yes/' /etc/ssh/sshd_config
RUN sed -ri 's/^#PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config

# set a password for root
RUN echo "root:pswd" | chpasswd

# expose 22 port
EXPOSE 22

# start up sshd
CMD ["/usr/sbin/sshd", "-D"]
