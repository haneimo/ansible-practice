# ubuntu20.04
FROM ubuntu:20.04

# system update
RUN apt-get update
RUN apt-get -y upgrade

# install sudo
RUN apt-get -y install sudo
# install ssh clients
RUN apt-get -y install openssh-client
RUN apt-get -y install sshpass

# install ansible
RUN apt-get -y install ansible 

# setttings
ADD ansible.cfg /etc/ansible
