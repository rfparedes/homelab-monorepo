FROM rockylinux/rockylinux:8
ARG SSH_KEY
ARG SSH_KEY_PUB
RUN dnf install -y ansible-core git
WORKDIR /root
RUN git clone https://github.com/rfparedes/homelab-monorepo.git 
RUN mkdir /root/.ssh
# Copy SSH keys passed as build args
RUN echo "$SSH_KEY" > /root/.ssh/id_rsa && \
    echo "$SSH_KEY_PUB" > /root/.ssh/id_rsa.pub && \
    chmod 600 /root/.ssh/id_rsa /root/.ssh/id_rsa.pub
ENTRYPOINT ["/bin/bash", "-c", "tail -f /dev/null"]