# Use a imagem oficial do Python 3.10
FROM python:3.10-slim

# Define o diretório de trabalho principal dentro do contêiner
WORKDIR /app

# Instala as dependências do sistema:
# - build-essential: Essencial para compilar bibliotecas Python complexas (reduz erros).
# - git: Para controle de versão e para o prompt customizado.
# - vim/nano: Editores básicos úteis no terminal.
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        build-essential \
        git \
        vim \
        nano \
    && rm -rf /var/lib/apt/lists/*

# Copia o arquivo de requisitos e o instala
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copia o .bashrc customizado para o diretório root do usuário (que é o padrão)
COPY .bashrc /root/.bashrc

# Define o comando padrão para iniciar o shell bash
CMD ["bash"]