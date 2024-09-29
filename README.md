# Gerenciamento de Usuários e Atendimentos

Este projeto utiliza **Prisma ORM** com **TypeScript** para gerenciar um banco de dados MySQL, que contém usuários e seus respectivos atendimentos (Customer Services).

## Tecnologias Utilizadas

- **Prisma ORM**
- **TypeScript**
- **MySQL**
- **Node.js**

## Estrutura do Banco de Dados

### Tabela `users`
```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    email VARCHAR(255) NOT NULL,
    password VARCHAR(255) NOT NULL
);
```

### Tabela `customer_services`
```sql
CREATE TABLE customer_services (
    id INT AUTO_INCREMENT PRIMARY KEY,
    customer_name VARCHAR(255) NOT NULL,
    company_name VARCHAR(255) NOT NULL,
    description VARCHAR(255) NOT NULL,
    date VARCHAR(255) NOT NULL,
    status VARCHAR(255) NOT NULL,
    users_id INT,
    FOREIGN KEY (users_id) REFERENCES users(id)
);
```

## Instalação e Configuração

1. Instale as dependências:
    ```bash
    npm install
    ```

2. Configure o banco de dados no arquivo `.env`:
    ```env
    DATABASE_URL="mysql://usuario:senha@localhost:3306/nome_do_banco"
    ```

3. Execute as migrações:
    ```bash
    npx prisma migrate dev --name init
    ```

4. Gere o cliente Prisma:
    ```bash
    npx prisma generate
    ```

5. Inicie o projeto:
    ```bash
    npm run dev
    ```

## Comandos Úteis

- Abrir o Prisma Studio:
    ```bash
    npx prisma studio
    ```

---
