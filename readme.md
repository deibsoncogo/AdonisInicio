# Iniciando com AdonisJS, um framework completo para NodeJS
Meu primeiro contato com o Adonis JS, conteúdo administrado pelo Diego Fernandes da Rocketseat

[![Run in Insomnia}](https://insomnia.rest/images/run.svg)](https://insomnia.rest/run/?label=Adonis%20Inicio&uri=https%3A%2F%2Fraw.githubusercontent.com%2Fdeibsoncogo%2FAdonisInicio%2Fmaster%2FInsomnia-All_2022-03-08.json)

## Anotações
A dependência Nodemon já vem instalada e mais algumas configurações feitas como uma migration de usuário e token

## Comandos
Para realizar a instalação do `Adonis JS` de forma global foi utilizado o seguinte comando com o `Yarn`
```bash
yarn global add @adonisjs/cli
```

Para criar o projeto utilizamos este comando, onde o `--api-only` defini que queremos uma aplicação sem views
```bash
adonis new adonisinicio --api-only
```

Foi criado dois controller com os seguintes comandos
```bash
adonis make:controller Auth
adonis make:controller App
```

### Banco de dados
Como vamos utilizar o `Postgres` como banco de dados devemos instalar seu driver
```bash
yarn add pg
```

Depois foi utilizado o seguinte comando para criar um container com o `Docker`
```bash
docker run --name AdonisInicio -e POSTGRES_DB=adonisinicioDB -e POSTGRES_USER=adonisinicio -e POSTGRES_PASSWORD=docker -p 5432:5432 -d postgres
```

Depois realizamos a configuração do arquivo `.env` para conseguir acessar o banco de dados
```bash
DB_CONNECTION=pg
DB_PORT=5432
DB_USER=adonisinicio
DB_PASSWORD=docker
DB_DATABASE=adonisinicioDB
```

Por fim executamos este comandos para criar os migrations que veio na aplicação
```bash
adonis migration:run
```

### Executando o servidor
Para dar inicio do servidor basta utilizar o seguinte comando onde ele vai rodar na porta 3333
```bash
adonis serve --dev
```
