FROM mcr.microsoft.com/devcontainers/java:1-11-bullseye

# Remove possíveis repositórios problemáticos
RUN rm -f /etc/apt/sources.list.d/yarn.list

RUN apt-get update || true

RUN apt-get install -y \
    git \
    curl \
    wget \
    unzip \
    && apt-get clean
    
# Define diretório de trabalho
WORKDIR /workspace

# Garante permissões corretas
RUN chown -R vscode:vscode /workspace
