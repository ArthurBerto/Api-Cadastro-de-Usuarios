# API de Gerenciamento de Usuários

Esta é uma API simples baseada em Express para gerenciar usuários. Ela fornece endpoints para criar, ler, atualizar e deletar usuários em um banco de dados utilizando o Prisma ORM.

## Índice
- [Visão Geral](#visão-geral)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Instalação](#instalação)
- [Endpoints da API](#endpoints-da-api)
  - [POST /usuarios](#post-usuarios)
  - [GET /usuarios](#get-usuarios)
  - [PUT /usuarios/:id](#put-usuariosid)
  - [DELETE /usuarios/:id](#delete-usuariosid)
- [Contribuindo](#contribuindo)
- [Licença](#licença)

## Visão Geral
Este projeto é uma API básica de gerenciamento de usuários onde é possível criar, consultar, atualizar e deletar usuários de um banco de dados. Os dados são armazenados em um banco de dados através do Prisma ORM, e o servidor é executado com Node.js utilizando o Express. A API também usa CORS para permitir requisições entre diferentes origens.

## Tecnologias Utilizadas
- **Node.js**: Ambiente de execução JavaScript
- **Express**: Framework web para Node.js
- **Prisma**: ORM (Mapeamento Objeto-Relacional) para gerenciamento do banco de dados
- **CORS**: Middleware para permitir requisições entre diferentes origens
- **PostgreSQL** (ou outro banco de dados suportado): Banco de dados para armazenar os dados dos usuários

## Instalação

1. Clone este repositório:

    ```bash
    git clone https://github.com/ArthurBerto/Api-Cadastro-de-Usuarios
    cd <diretório-do-repositório>
    ```

2. Instale as dependências:

    ```bash
    npm install
    ```

3. Configure o banco de dados:
   Certifique-se de configurar o Prisma e o banco de dados corretamente. Para PostgreSQL, você pode usar:

   ```bash
   npx prisma migrate dev
   ```

4. Execute o aplicativo:

    ```bash
    npm start
    ```

5. O servidor será iniciado em `http://localhost:3000`.

## Endpoints da API

### POST /usuarios
Cria um novo usuário.

#### Corpo da Requisição:
```json
{
  "email": "usuario@exemplo.com",
  "name": "João Silva",
  "age": 30
}
```

#### Resposta:
```json
{
  "email": "usuario@exemplo.com",
  "name": "João Silva",
  "age": 30
}
```
Código de Status: `201 Created`

### GET /usuarios
Retorna uma lista de todos os usuários ou filtra os usuários pelos parâmetros de consulta.

#### Parâmetros de Consulta:
- `name`: Nome do usuário.
- `email`: E-mail do usuário.
- `age`: Idade do usuário.

#### Exemplo de Requisição:
```bash
GET /usuarios?name=João
```

#### Resposta:
```json
[
  {
    "id": 1,
    "email": "usuario@exemplo.com",
    "name": "João Silva",
    "age": 30
  }
]
```
Código de Status: `200 OK`

### PUT /usuarios/:id
Atualiza um usuário pelo ID.

#### Corpo da Requisição:
```json
{
  "email": "novo-email@exemplo.com",
  "name": "Novo Nome",
  "age": 35
}
```

#### Resposta:
```json
{
  "email": "novo-email@exemplo.com",
  "name": "Novo Nome",
  "age": 35
}
```
Código de Status: `201 Created`

### DELETE /usuarios/:id
Deleta um usuário pelo ID.

#### Resposta:
```json
{
  "message": "Usuário deletado com sucesso!"
}
```
Código de Status: `200 OK`
