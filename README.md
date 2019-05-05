# Node Store

API de uma Store feita em Node.js onde contém o cadastro de clientes, produtos e pedidos, utilizando autenticação e nível de cliente.

Segue abaixo exemplos de chamadas da api.

## **Cadastro de clientes**
Para o cliente existem dois tipos, sendo o admin e o user, por padrão é cadastrado o role user, em alguns métodos da API, somente o perfil admin pode fazer determinadas inclusões, como no caso a inclusão de produtos.

*POST* customers

    {
        "name": "Ricardo",
        "email": "ricardocavalcantesilva@gmail.com",
        "password": "ric456",
        "roles": [
            "admin",
            "user"
        ]
    }

## **Gerando um token de autenticação**
Gera um token para um usuário já existente.

*POST* customers/authenticate

    {
    	"email":"ricardocavalcantesilva@gmail.com",
    	"password":"ric456"
    }

## **Realizar refresh no token**
Gera um novo token. Deve passar no Headers **x-access-token** o token atual.

*POST* customers/refresh-token

    {
    	"email":"ricardocavalcantesilva@gmail.com",
    	"password":"ric456"
    }

## **Incluir um novo produto**
Incluir um novo produto, neste caso somente um usuário com a role do tipo admin que poderá fazer tal inclusão. Deve passar no Headers **x-access-token** o token atual.

*POST* products

    {
        "title": "Teclado Gamer",
        "slug": "teclado-gamer",
        "description": "Teclado Gamer",
        "price": "399",
        "active": "true",
        "tags": [
            "informatica",
            "teclado",
            "games"
        ]
    }

## **Atualizar um produto**
Atualizar um produto, neste caso somente um usuário com a role do tipo admin que poderá fazer tal atualização. Deve passar no Headers **x-access-token** o token atual.

*PUT* products/[Produto ID]

    {
        "title": "Teclado Gamer XPTO",
        "slug": "teclado-gamer",
        "description": "Teclado Gamer",
        "price": "499"
    }

## **Excluir um produto**
Exclui um produto, neste caso somente um usuário com a role do tipo admin que poderá fazer tal exclusão. Deve passar no Headers **x-access-token** o token atual.

*DEL* products

    {
    	"id": "5cc95d160157351a34d02d89"
    }


## **Recuperar todos os produtos**
Retorna todos os produtos cadastrados, neste caso somente um usuário com a role do tipo admin que poderá fazer tal solicitação. Deve passar no Headers **x-access-token** o token atual.

*GET* products

## **Recuperar produto pelo slug**
Retorna todos os produtos cadastrados com o slug informado, neste caso somente um usuário com a role do tipo admin que poderá fazer tal solicitação. Deve passar no Headers **x-access-token** o token atual.

*GET* products/[Slug do produto]

## **Recuperar produto pelo Id**
Retorna todos os produtos cadastrados com o ID informado, neste caso somente um usuário com a role do tipo admin que poderá fazer tal solicitação. Deve passar no Headers **x-access-token** o token atual.

*GET* products/admin/[Id do produto]

## **Recuperar produto pela tag**
Retorna todos os produtos cadastrados com a Tag informada, neste caso somente um usuário com a role do tipo admin que poderá fazer tal solicitação. Deve passar no Headers **x-access-token** o token atual.

*GET* products/tags/[Tag do produto]

## **Incluir um pedido**
Inclui um novo pedido.

*POST* orders

    {
        "title": "Teclado Gamer",
        "slug": "teclado-gamer",
        "description": "Teclado Gamer",
        "price": "399",
        "active": "true",
        "tags": [
            "informatica",
            "teclado",
            "games"
        ]
    }

## **Recuperar todos os pedidos**
Retorna todos os pedidos cadastrados, neste caso somente um usuário com a role do tipo admin que poderá fazer tal solicitação. Deve passar no Headers **x-access-token** o token atual.

*GET* orders
