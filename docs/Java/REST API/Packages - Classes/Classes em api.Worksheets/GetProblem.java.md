# GetProblem.java
Esta classe do tipo Servlet representa um endpoint da API que tem como objetivo obter um problema específico da base de dados.
<br>
Ao receber um pedido HTTP, este endpoint verifica a validade do token JWT fornecido no corpo do pedido para garantir a autorização do utilizador.

### Como utilizar este endpoint?
1. Dependendo da maneira como estiver a correr o projeto, deverá utilizar um dos dois URL's abaixo:
    - Se o projeto estiver a ser corrido localmente, deverá usar o URL <http://localhost:8080/api/GetProblem>
    - Se o projeto estiver a ser corrido remotamente, deverá usar o URL <http://ram.ipt.pt:8080/api/GetProblem>
2. Deverá enviar (em formato **JSON**) no corpo do pedido HTTP os seguintes parâmetros:
    - `"id"`: parâmetro do tipo int. Contém o ID do problema que se pretende obter.
    - `"jwtToken"`: parâmetro do tipo string. Contém o token JWT que autoriza o utilizador a realizar a operação.
3. O endpoint retorna o problema correspondente ao ID fornecido na base de dados se o token JWT for válido.

### Exemplo de um pedido enviado para este endpoint
```json
{
    "id": 123,
    "jwtToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c..."
}
```
### Exemplo de uma resposta bem sucedida (código 200 OK)
```json
{
    "point": 1.0,
    "inputs": {
        "": "Olá Mundo"
    },
    "difficulty": 1,
    "id": 1,
    "language": 1,
    "author": "authorUsername",
    "date": "16/05/2022",
    "descript": "<p style=\\\"text-align: center;\\\"><strong><span style=\\\"color: rgbrgb(65, 168, 95); font-size: 18px;\\\">Construa um algoritmo que imprima na consola a mensagem:\r\nOlá Mundo</span></strong></p>",
    "image": "data:image/png;base64,/9j/4AAQSkZJRgABAgAAAQABAAD/2wBDAAEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQICAQECAQEBAgICAgICAgICAQICAgICAgICAgL/2wBDAQEBAQEBAQEBAQECAQEBAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgL/wAARCAA6AHYDASIAAhEBAxEB/8QAHwAAAQUBAQEBAQEAAAAAAAAAAAECAwQFBgcICQoL/8QAtRAAAgEDAwIEAwUFBAQAAAF9AQIDAAQRBRIhMUEGE1FhByJxFDKBkaEII0KxwRVS0fAkM2JyggkKFhcYGRolJicoKSo0NTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uHi4+Tl5ufo6erx8vP09fb3+Pn6/8QAHwEAAwEBAQEBAQEBAQAAAAAAAAECAwQFBgcICQoL/...",
    "solver": "    begin MainProgram\n        write \"Olá Mundo\"\n    end MainProgram\n\n",
    "tags": null,
    "title": "Olá Mundo",
    "updateauthor": null,
    "updatedate": null,
    "videolink": "https://www.youtube.com/embed/test",
    "code": null,
    "userEfficacy": 0.0,
    "userEfficiency": 0.0,
    "userOriginality": 0.0
}
```
### Exemplo de uma resposta mal sucedida (código 401 - UNAUTHORIZED)
Se token enviado não for válido, o servidor devolve ```"401 - Token not valid"```. Isto significa que o token ***JWT*** enviado não é válido. Isto pode acontecer em várias situações, como por exemplo, se o token já não existir.