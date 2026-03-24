FROM mcr.microsoft.com/devcontainers/java:1-11-bullseye

# Instala ferramentas adicionais úteis
RUN apt-get update && apt-get install -y \
    git \
    curl \
    wget \
    unzip \
    && apt-get clean

# Define diretório de trabalho
WORKDIR /workspace

# Garante permissões corretas
RUN chown -R vscode:vscode /workspace