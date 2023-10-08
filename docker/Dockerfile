# Installs and initializes SSH server by default
FROM ubuntu:latest

RUN apt update; \
    apt install -y ssh; \
    apt clean;

RUN mkdir /var/run/sshd; \
    mkdir -p /root/.ssh;

RUN sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config; \
    sed -i 's/#PubkeyAuthentication yes/PubkeyAuthentication yes/' /etc/ssh/sshd_config;

COPY keys/docker.pub /root/.ssh
RUN cat /root/.ssh/docker.pub > /root/.ssh/authorized_keys

EXPOSE 22
EXPOSE 8123
CMD [ "/usr/sbin/sshd", "-D" ]