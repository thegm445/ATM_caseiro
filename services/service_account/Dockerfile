# services/service_account/Dockerfile
FROM python:3.12-slim

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

WORKDIR /usr/src/app

# Instalar dependências do sistema, se necessário (ex: build-essential para psycopg2)
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    libpq-dev \
    && rm -rf /var/lib/apt/lists/*

# Copiar requirements e instalar dependências Python
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copiar o resto do código do serviço
COPY . .

# O comando para rodar é definido no docker-compose.yml
# EXPOSE 8001 (opcional, pois já está no docker-compose)
