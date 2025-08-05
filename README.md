# 🐬 MySQL com Docker Compose

Este repositório demonstra como subir um banco de dados **MySQL** com persistência de dados usando **Docker Compose**, de forma simples, rápida e organizada.

---

## 📁 Estrutura de Diretórios

---

## ⚙️ Arquivo `docker-compose.yml`


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
🛠️ Imagem: MySQL oficial

🧱 Container: my-mysql

🔒 Senha root: mysqlPW

🗂️ Banco criado automaticamente: mysqlDB

📦 Volume local: mysql-volume (para persistência dos dados)

🔁 Restart: sempre que necessário

💻 Comandos Utilizados
bash
Copiar
Editar
cd Documents
mkdir mysql2
cd mysql2
echo > docker-compose.yml
start docker-compose.yml
docker-compose up -d
✅ Resultado Esperado
Após executar docker-compose up -d, o terminal exibirá o processo de criação da imagem e inicialização do container:

📦 Download automático da imagem do MySQL

🚀 Container iniciado em segundo plano (-d)

🟢 MySQL acessível na porta 3306

🔌 Conexão com o Banco
Use qualquer cliente MySQL (CLI ou GUI) com os seguintes dados:

bash
Copiar
Editar
Host:     127.0.0.1
Porta:    3306
Usuário:  root
Senha:    mysqlPW
Banco:    mysqlDB
🧽 Parar o Container
bash
Copiar
Editar
docker-compose down
Isso para o container, mas mantém os dados salvos no volume.

📝 Observações
🔁 O volume mysql-volume mantém os dados mesmo se o container for recriado.

🧹 Use docker volume rm mysql2_mysql-volume se quiser apagar os dados persistentes.
