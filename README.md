
# Allfit Backend

Api do aplicativo Allfit

## Índice

- [Pré-requisitos](#pré-requisitos)
- [Configuração do Projeto](#configuração-do-projeto)
- [Executando o Projeto](#executando-o-projeto)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Comandos Úteis](#comandos-úteis)
- [Tecnologias Usadas](#tecnologias-usadas)

## Pré-requisitos

Antes de começar, certifique-se de ter as seguintes ferramentas instaladas:

- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/install/)
- [Node.js](https://nodejs.org/) (apenas se quiser executar localmente sem Docker)

## Configuração do Projeto

1. Clone este repositório:

   ```bash
   git clone https://github.com/VitorAPN/allfit-api
   cd allfit-api
   ```

2. Instale as dependências (caso esteja executando localmente):

   ```bash
   npm install
   ```

## Executando o Projeto

### Usando Docker

O projeto já vem preparado para ser executado com Docker, o que facilita a inicialização do banco de dados PostgreSQL e do servidor NestJS.

1. No diretório raiz do projeto, execute:

   ```bash
   docker-compose up --build
   ```

   Isso irá construir as imagens necessárias e iniciar o servidor NestJS junto com um contêiner do PostgreSQL.

2. O servidor NestJS estará disponível em:

   ```
   http://localhost:3000
   ```

3. Para verificar o banco de dados PostgreSQL:

   - Host: `localhost`
   - Porta: `5432`
   - Usuário: conforme especificado no arquivo `.env`
   - Senha: conforme especificado no arquivo `.env`
   - Nome do banco: conforme especificado no arquivo `.env`

### Sem Docker (Execução Local)

Se preferir executar o NestJS diretamente no seu ambiente local (sem Docker), siga os seguintes passos:

1. Instale as dependências (caso ainda não tenha feito):

   ```bash
   npm install
   ```

2. Certifique-se de que o PostgreSQL está rodando na sua máquina, com as mesmas credenciais que estão no arquivo `.env`.

3. Execute o servidor NestJS:

   ```bash
   npm run start:dev
   ```

   O servidor estará rodando em `http://localhost:3000`.

## Estrutura do Projeto

Aqui está uma visão geral da estrutura do projeto:

```bash
├── src
│   ├── app.module.ts
│   ├── main.ts
│   ├── modules
│   │   └── exemplo
│   │       ├── exemplo.module.ts
│   │       ├── exemplo.controller.ts
│   │       └── exemplo.service.ts
├── docker-compose.yml
├── Dockerfile
├── .env
├── package.json
└── README.md
```

## Comandos Úteis

- Para construir o projeto:

  ```bash
  npm run build
  ```

- Para executar os testes:

  ```bash
  npm run test
  ```

- Para executar o linter:

  ```bash
  npm run lint
  ```

## Tecnologias Usadas

- [NestJS](https://nestjs.com/)
- [TypeScript](https://www.typescriptlang.org/)
- [PostgreSQL](https://www.postgresql.org/)
- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)
