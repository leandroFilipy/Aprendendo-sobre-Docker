🚀 MySQL com Docker Compose
Este repositório mostra como subir um contêiner MySQL de forma simples e rápida usando Docker Compose.

📁 Estrutura de diretórios
markdown
Copiar
Editar
Documents/
  ├── mysql/
  └── mysql2/
       └── docker-compose.yml
⚙️ Configuração do docker-compose.yml
yaml
Copiar
Editar
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
✅ image: mysql/mysql-server:latest
✅ container_name: my-mysql
✅ restart: reinicia sempre que houver falha
✅ environment:

MYSQL_DATABASE: cria o banco mysqlDB

MYSQL_ROOT_PASSWORD: define a senha do root
✅ ports: expõe a porta 3306
✅ volumes: persistência dos dados

🖥️ Comandos utilizados
bash
Copiar
Editar
cd documents
mkdir mysql2
cd mysql2
echo > docker-compose.yml
start docker-compose.yml
docker-compose up -d
📦 Resultado
✅ O Docker realizou o download das camadas necessárias da imagem MySQL
✅ O serviço subiu em modo detached e está rodando no contêiner my-mysql
✅ O banco de dados está acessível na porta 3306

🔗 Como acessar
🔹 Você pode acessar o banco de dados via qualquer cliente MySQL, por exemplo:

bash
Copiar
Editar
mysql -h 127.0.0.1 -P 3306 -u root -p
(use a senha mysqlPW definida no docker-compose.yml)

📌 Observações
O volume mysql-volume garante que os dados não sejam perdidos caso o contêiner seja reiniciado.

O comando docker-compose down pode ser usado para parar e remover o contêiner sem apagar os dados.
