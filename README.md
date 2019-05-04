# Node Store

API de uma Store feita em Node.js onde contém o cadastro de clientes, produtos e pedidos, utilizando autenticação e nível de cliente.

Segue abaixo exemplos de chamadas da api.

Em algumas requisições deverá informar em Headers **x-access-token** o token gerado no *POST* customers/authenticate


**Cadastro de clientes**

*POST* customers

    {
        "name": "Ricardo",
        "email": "ricardocavalcantesilva@gmail.com",
        "password": "ric456"
    }

**Gerando um token de autenticação**

*POST* customers/authenticate

    {
    	"email":"ricardocavalcantesilva@gmail.com",
    	"password":"ric456"
    }

**Realizar refresh no token**

*POST* customers/refresh-token

    {
    	"email":"ricardocavalcantesilva@gmail.com",
    	"password":"ric456"
    }

**Incluir um novo produto**
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

**Atualizar um produto**
*PUT* products/[Produto ID]

    {
        "title": "Cadeira Gamer",
        "slug": "cadeira-gamer",
        "description": "Cadeira Gamer",
        "price": "999"
    }

**Excluir um produto**
*DEL* products

    {
    	"id": "5cc95d160157351a34d02d89"
    }


**Recuperar todos os produtos**
*GET* products

**Recuperar produto pelo slug**
*GET* products/[Slug do produto]

**Recuperar produto pelo Id**
*GET* products/[Id do produto]

**Recuperar produto pela tag**
*GET* products/tags/[Tag do produto]

**Incluir um pedido**
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

**Recuperar todos os pedidos**
*GET* orders
