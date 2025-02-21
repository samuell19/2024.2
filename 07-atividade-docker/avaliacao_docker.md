# Docker compose com Django e banco de dados

## Informações gerais

- Assunto: Docker, conteinizar aplicativos
- Disciplina: *sistemas operacionais*
- **Tarefa**:
  1. Criar um projeto django com uma aplicação web
    - alternativa, criar uma _branch_ no repositório do projeto integrador para configurar o acesso ao repositório de dados
  2. Criar um `Dockerfile` para o projeto django
  3. Criar a imagem e testar o conteiner para testar
  4. OPCIONAL, porque dependendo de como pergunta ao assistente de IA; criar um `Dockerfile` para o repositório de banco de dados
  5. Criar um `docker-compose.yml` e configurar para 2 serviços: `webapp` e `db`
  6. Configurar o arquivo django de acesso ao repositório de dados para usar o serviço docker `db`
  7. Testar o `docker-compose.yml`
  8. Relatar minimamente o que foi feito.
- **Entrega**: copia desse aquivo markdown preenchido, no seu repositório _fork_ de https://github.com/sistemas-operacionais/2024.2


## Relatório

### Aluno

- nome: Samuel Medeiros de Oliveira
- matrícula: 20232014040009

### Relato
<h1>Docker File</h1>
<div>
<pre>
FROM python:3.12.1

# Diretório de trabalho: /app
WORKDIR /app

# Copiando arquivos
COPY . /app/

# Instalando dependências
RUN pip install --upgrade pip && \
    pip install -r requirements.txt --verbose

# Executando coleta de arquivos estáticos
RUN python manage.py collectstatic --noinput

# Expondo a porta 8000
EXPOSE 8000

# Comando para iniciar o servidor
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]

# Primeiro, crie o arquivo de requisitos: pip freeze > requirements.txt
# Este arquivo será utilizado pelo Dockerfile para instalar as dependências
# Para construir a imagem, utilize:
# docker build --no-cache -t rn-semfila .
# Para executar o container:
# docker run -p 8000:8000 rn-semfila (pode ser alterado posteriormente)
# Para executar utilizando volumes:
# docker run -it -v /local:/app -p 8000:8000 rn-semfila
# Quando se utiliza volumes, as alterações no projeto local são refletidas no container
# Dessa forma, também é possível acessar o terminal do container
# Forma alternativa de executar o container:
# docker run -it -v /local:/app -p 8000:8000 rn-semfila python manage.py runserver
# Dessa forma, é possível executar o servidor do Django diretamente no container
</pre>
</div>

<h1>Docker compose</h1>
<div>
<pre>
services:
  db:
    image: postgres:13
    volumes:
      - postgres_data:/var/lib/postgresql/data/
    environment:
      POSTGRES_USER: your_postgres_user # usuário do postgres
      POSTGRES_DB: your_database_name # nome do banco de dados
      POSTGRES_HOST_AUTH_METHOD: trust # autenticação do banco de dados/trust
    ports:
      - "5432:5432" # opcional
  web:
    build: .
    ports:
      - "5000:5000"
    volumes:
      - .:/app
    command: python run.py
    depends_on:
      - db
    environment:
      DATABASE_URL: postgres://seu_usuario@db:5432/seu_banco_de_dados
</pre>
</div>

### Arquivos docker e de configuração do django


**observação** coloque nomes nos arquivos antes do códigos-fonte.