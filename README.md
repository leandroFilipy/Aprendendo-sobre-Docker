# 🐬 GUIA MASTER MYSQL DOCKER - TOPZERA 🚀

Guia rápido para subir o banco de dados e configurar tudo de uma vez.

---

### 🛠️ 1. Comandos de Preparação (Bash/Terminal)
Execute estes comandos para criar a pasta e o arquivo:

```bash
cd documents
mkdir mysql2
cd mysql2
echo > docker-compose.yml
start docker-compose.yml

📄 2. Configuração do Arquivo (docker-compose.yml)
Cole este conteúdo dentro do arquivo docker-compose.yml:

YAML
version: '3.8'
services:
  db:
    image: mysql/mysql-server:latest
    container_name: my-mysql
    restart: always
    environment:
      - MYSQL_DATABASE=mysqlDB
      - MYSQL_ROOT_PASSWORD=mysqlPW
    ports:
      - '3306:3306'
    volumes:
      - mysql-volume:/var/lib/mysql

volumes:
  mysql-volume:
    driver: local


🚀 3. Subir e Configurar o Banco (Docker + SQL)
Copie e cole a sequência abaixo no seu terminal:

# Subir o container
docker-compose up -d

# Entrar no container e logar no MySQL (Senha: mysqlPW)
docker exec -it my-mysql bash
mysql -u root -p

# --- COMANDOS SQL (DENTRO DO MYSQL) ---
CREATE DATABASE LEANDRODATABASE;

UPDATE mysql.user SET host='%' WHERE user='root';

FLUSH PRIVILEGES;
