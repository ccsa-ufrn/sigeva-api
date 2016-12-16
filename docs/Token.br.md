# Token

Entidade responsável pela geração de tokens utilizados pelo sistema.

## POST /token/authentication

Rota pública para autenticação e recebimento de um token. É necessário enviar 
o **mail** e a **password** em method *POST* para realizar a autenticação. 

### Queries
Não permite queries.

### Parâmetros

Parâmetros | Descrição 
-----------|-----------
mail | O email do usuário cadastrado 
password | A senha do usuário

### Permissões
Rota pública

### Respostas

O resultado da requisição:

~~~ json
{
    "status": "success|error",
    "msg": "user not exists|wrong password|disabled user",
    "errorcode": 1 2 3,
    "token": "[jwt_token]"
}
~~~