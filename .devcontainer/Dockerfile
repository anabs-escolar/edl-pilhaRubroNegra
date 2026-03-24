FROM mcr.microsoft.com/devcontainers/java:1-11-bullseye

# Remove apenas o Yarn (não quebra o sistema)
RUN rm -f /etc/apt/sources.list.d/yarn.list

# Instala Maven + ferramentas úteis
RUN apt-get update && apt-get install -y \
    maven \
    git \
    curl \
    wget \
    unzip \
    && apt-get clean

WORKDIR /workspace

RUN chown -R vscode:vscode /workspace
