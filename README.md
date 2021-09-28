# *Contacts Api*

API para armazenar contatos de usuários.

Desenvolvida como atividade do Mini Curso de Ruby on Rails

## Instalação

```sh
    $ bundle install
```

## Iniciar Banco de Dados

- Verifique as credenciais do banco de dados em `contacts-api/config/database.yml`

- Execução:

```sh
    $ rails db:migrate
```

## Iniciar servidor

```
    $ rails s
```

## Rotas

- Url base: `localhost:3000/api/v1`

|Tipo|Rota|Descrição|Retorno|
|--|--|--|--|
|GET|`/contacts/`|Listar todos os contatos do usuário|Lista de todos os contatos|
|GET|`/contacts/:id`|Listar um contato com o id|JSON do contato|
|POST|`/contacts/`|Adicionar um novo contato|JSON do contato|
|PUT|`/contacts/:id`|Editar os dados de um contato|JSON do contato|
|DELETE|`/contacts/:id`|Deletar um contato existente||

## Objeto User

```json
    {
        "email": String,
        "password": String,
    }
```
## Objeto Contact


```json
    {
        "name": String,
        "phone": String,
        "description": Text,
        "user": references,
    }
```
#

Para acessar as endpoints é preciso um token de autenticação obtido através da criação de um novo usuário.

## Criar usuário

```
    $ rails c
    $ User.create(email: 'example@email.com', password: 'example' )
```