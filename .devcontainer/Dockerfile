# Dockerfile for development container

FROM ubuntu:20.04

# Install necessary packages
RUN apt-get update && apt-get install -y \
    zsh \
    curl \
    build-essential \
    python3 \
    python3-pip \
    git \
    build-essential \
    npm \
    lsof \
    procps \
    vim \
    less \
    net-tools \
    sudo \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# Set up work directory
WORKDIR /workspace

# Create the vscode user and group with the expected UID and GID (1000)
RUN groupadd -g 1000 reconpoint && \
    useradd -m -u 1000 -g 1000 -s /bin/zsh reconpoint && \
    echo "reconpoint ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

# Set default shell to Zsh
SHELL ["/bin/zsh", "-c"]

RUN echo 'export PS1="%~ %# "' >> /home/reconpoint/.zshrc

# Set the default user
USER reconpoint
