# GetWorksheet.java

Esta classe do tipo Servlet representa um endpoint da API que tem como objetivo obter uma folha de exercícios da base de dados.

### Como utilizar este endpoint?

1. Dependendo da maneira como estiver a correr o projeto, deverá utilizar um dos dois URL's abaixo:
    - Se o projeto estiver a ser corrido localmente, deverá usar o URL <http://localhost:8080/api/GetWorksheet>
    - Se o projeto estiver a ser corrido remotamente, deverá usar o URL <http://ram.ipt.pt:8080/api/GetWorksheet>
2. Deverá enviar (em formato **JSON**) no corpo do pedido HTTP os seguintes parâmetros:
    - `"id"`: parâmetro do tipo int. Contém o ID da ficha de exercícios que deseja obter.
    - `"jwtToken"`: parâmetro do tipo string. Contém o token JWT que autoriza o utilizador a realizar a operação.
3. O endpoint retorna uma folha de exercícios da base de dados se o token JWT for válido e se o ID da folha de exercícios existir na base de dados.

### Exemplo de um pedido enviado para este endpoint

```json
{
    "id": 1,
    "jwtToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c..."
}
```

### Exemplo de uma resposta bem sucedida (código 200 OK)
```json
{
    "problems": [
        1,
        6,
        20,
        19,
        4
    ],
    "courseID": 1,
    "id": 123,
    "number": 3,
    "author": "username",
    "date": "2024-02-19 18:54",
    "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAQAAAAEACAIAAADTED8xAAADMElEQVR4nOzVwQnAIBQFQYXff81RUkQCOyDj1YOPnbXWPmeTRef+/3O/OyBjzh3CD95BfqICMK0CMK0CMK0CMK0...",
    "sentdate": "2024-02-19",
    "title": "WorksheetTitle",
    "updateauthor": "",
    "updatedate": ""
}
```

### Exemplo de uma resposta mal sucedida (código 401 - UNAUTHORIZED)
Se token enviado não for válido, o servidor devolve ```"401 - Token not valid"```. Isto significa que o token ***JWT*** enviado não é válido. Isto pode acontecer em várias situações, como por exemplo, se o token já não existir.