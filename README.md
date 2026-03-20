# 🐬 Guia Master MySQL + Docker 🚀

Guia rápido e organizado para subir um banco de dados **MySQL com Docker**.

---

# 🛠️ 1. Preparação do Ambiente

Execute os comandos abaixo no terminal:

```bash
cd ~/Documents

mkdir mysql-docker

cd mysql-docker

echo > docker-compose.yml
```


---

# 📄 2. Configuração do Docker Compose

Abra o arquivo `docker-compose.yml` e cole:

```yaml
version: '3.8'

services:
  db:
    image: mysql:8.0
    container_name: my-mysql
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: mysqlPW
      MYSQL_DATABASE: mysqlDB
    ports:
      - "3306:3306"
    volumes:
      - mysql-volume:/var/lib/mysql

volumes:
  mysql-volume:
```

---

# 🚀 3. Subindo o Container

```bash
docker compose up -d
```

---

# 🔐 Acessando o MySQL

Execute os comandos abaixo **um por vez**:

### 1️⃣ Entrar no container

```bash id="cmd1"
docker exec -it my-mysql bash
```

---

### 2️⃣ Acessar o MySQL dentro do container

```bash id="cmd2"
mysql -u root -p
```

🔑 Quando pedir senha, digite:

```
mysqlPW
```

---

💡 **Resumo:**

* Primeiro você entra no container 🐳
* Depois acessa o MySQL 🐬


---

# 🧠 5. Configuração do Banco (SQL)

```sql
CREATE DATABASE leandro_database;

ALTER USER 'root'@'%' IDENTIFIED BY 'mysqlPW';

FLUSH PRIVILEGES;
```

---

# 🌐 6. Acesso

* Host: localhost
* Porta: 3306
* Usuário: root
* Senha: mysqlPW

---

# ⚠️ Boas Práticas

* 🔒 Use senhas fortes em produção
* 📦 Evite usar latest
* 💾 Sempre use volumes

---

# 👨‍💻 Autor

**Leandro Mogador ++ 🚀**

---

# ⭐ Conclusão

Setup simples, rápido e pronto pra desenvolvimento com Docker + MySQL.
