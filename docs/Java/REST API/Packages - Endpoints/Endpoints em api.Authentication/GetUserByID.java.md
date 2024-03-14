# GetUserByID.java
Esta classe do tipo Servlet representa um endpoint da API que tem como objetivo obter um utilizador registado no sistema, dado o seu ID.

### Como utilizar este endpoint?
- Dependendo da maneira como estiver a correr o projeto, deverá utilizar um dos dois URL's abaixo:
    - Se o projeto estiver a ser corrido localmente, deverá usar o URL <http://localhost:8080/AlgorithmiBO/api/GetUserByID>
    - Se o projeto estiver a ser corrido remotamente, deverá usar o URL <http://ram.ipt.pt:8080/AlgorithmiBO/api/GetUserByID>
- Deverá enviar (em formato **JSON**) no corpo do pedido HTTP os seguintes parâmetros:
    - `"id"` : parâmetro do tipo int. Contém o ID que identifica o utilizador na base de dados
    - `"jwtToken"`: parâmetro do tipo string. Contém o token JWT que autoriza o utilizador a realizar a operação

### Exemplo de um pedido enviado para este endpoint
```json
{
    "id" : 123,
    "jwtToken":"eyJraWQiOiIwbHRLaHNUMFhSK1lyV0ZoaElrOWhBUUl6ZzRBOHF4L1IyVHQxekxBUmZZPSIsImFsZyI6IkhTMjU2In0.eyJ1c2VySUQiOjYsInVzZXJGaXJzdE5hbWUiOiJSb2RyaWdvIiwidXNlckxhc3ROYW1lIjoiU2VycmEiLCJ1c2VyVXNlcm5hbWUiOiJyc2VycmEiLCJ1c2VyRW1haWwiOiJhbHVubzI0MTgwQGlwdC5wdCIsInVzZXJJbWFnZSI6ImRhdGE6aW1hZ2UvcG5nO2Jhc2U2NCxpVkJPUncwS0dnb0FBQUFOU1VoRVVnQUFBZG9BQUFIYUNBWUFBQUNuNUlpdkFBQUFCSE5DU1ZRSUNBZ0lmQWhraUFBQUlBQkpSRUZVZUY3c3ZZdDYyN2pTcGUyRGZFaDZ6elAzZnpYL014YzA4L1h1VXhMYmt2LzFyc0lpSVlpVVpNZEpKOTFtSXBNNEZRb0ZvQllLQU1IT..."
}
```

### Exemplo de uma resposta bem sucedida (código 200)
```json
{
        "id": 3,
        "firstName": "User1",
        "lastName": "LastNameUser1",
        "username": "username",
        "password": null,
        "email": "email@ipt.pt",
        "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAIAAAACACAYAAADDPm...",
        "active": true,
        "role": 3,
        "language": 34,
        "course": 1,
        "updateUser": 3,
        "languageCode": "pt_pt"
    }
```

### Exemplo de uma resposta mal sucedida (código 401 - UNAUTHORIZED)
Se token enviado não for válido, o servidor devolve ```"401 - Token not valid"```. Isto significa que o token ***JWT*** enviado não é válido. Isto pode acontecer em várias situações, como por exemplo, se o token já não existir.