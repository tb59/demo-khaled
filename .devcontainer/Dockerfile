FROM ubuntu:24.04
ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        build-essential \
        gcc \
        curl \
        make \
        valgrind \
        clang \
        manpages \
        git \
        lowdown \
        gdb \
        sudo \
    && rm -rf /var/lib/apt/lists/*

RUN useradd -m -s /bin/bash pse
RUN usermod -aG sudo pse
RUN echo "pse ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/pse && chmod 0440 /etc/sudoers.d/pse
WORKDIR /workspace
USER pse
CMD ["/bin/bash"]
