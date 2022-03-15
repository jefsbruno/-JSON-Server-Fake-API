### Register

Para cadastrar um novo usuário é necessário user o endPoint /register nas seguintes condições:

POST/register

{
"email": "jeferson.teste@livee.com",
"password":"123456",
"name": "jefs",
"age": 26,
"favoriteTechs": []
}

formato da resposta:

{
"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImplZmVyc29uLnRlc3RlQGxpdmVlLmNvbSIsImlhdCI6MTY0NzE5Nzc3NCwiZXhwIjoxNjQ3MjAxMzc0LCJzdWIiOiI1In0.TKXXIGmzBaHXkoL2IP6mAr7HQLDDsmbwsdIgK95X4Sc",
"user": {
"email": "jeferson.teste@livee.com",
"name": "jefs",
"age": 26,
"favoriteTechs": [],
"id": 5
}
}

### LOGIN

para realizar o login

POST/login

{
"email": "jeferson.teste@livee.com",
"password":"123456"
}

formato da resposta:

{
"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImplZmVyc29uLnRlc3RlQGxpdmVlLmNvbSIsImlhdCI6MTY0NzE5Nzg1MywiZXhwIjoxNjQ3MjAxNDUzLCJzdWIiOiI1In0.mTJoeeSpuRqUiUNA9KLYsV4nlXmUEi_S-GaGmK0EPws",
"user": {
"email": "jeferson.teste@livee.com",
"name": "jefs",
"age": 26,
"favoriteTechs": [],
"id": 5
}
}

### Cadasto de Animais - Necessário autorização

Para realizar o cadastro de animais é necessario a autorização.

Authorization: Bearer {token}

POST/animals

{
"type": "piriquito",
"name": "Kiwi",
"userId": 5
}

lembrando que o userId: tem que ser o id do usuario que fez o login.

formato da resposta:

{
"type": "piriquito",
"name": "Kiwi",
"userId": 2,
"id": 2
}

### Vizualizar os animais Cadastrados - não é necessario autorização.

Para vizualizar todos os animais cadastros na api, você deve realizar um get no endpoint /animals.

GET/animal

formato da resposta:

{
"type": "piriquito",
"name": "Kiwi",
"userId": 5,
"id": 5
}

### Cadastra Favorite Fodd - necessário usuario está logado.

Authorization: Bearer {token}

POST/favoritefood

{
"name_food": "Pizza",
"userId": 5
}

formato da resposta:

{
"name_food": "Pizza",
"userId": 5,
"id": 5
}

### Vizualizar Favorite Food cadastradas - necessário usuario está logado.

Para realizar a vizualização das comidas cadastradas é necessario a autorização.

Authorization: Bearer {token}

para ter acesso ao cadastro precisamos realizar um GET no endpoint /favoritefood.

GET/favoritefood

formato da resposta:

{
"name_food": "Pizza",
"userId": 5,
"id": 5
}
