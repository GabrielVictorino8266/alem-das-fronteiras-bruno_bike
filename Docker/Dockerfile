# Imagem base da API — instala dependências e sobe o servidor
FROM python:3.14-rc-slim

WORKDIR /app

# Dependências de sistema necessárias para compilar o psycopg2
RUN apt-get update && apt-get install -y \
    gcc \
    libpq-dev \
    python3-dev \
    build-essential \
    && rm -rf /var/lib/apt/lists/*

COPY pyproject.toml .
RUN pip install psycopg2 --no-binary psycopg2
RUN pip install .

COPY . .

EXPOSE 8000