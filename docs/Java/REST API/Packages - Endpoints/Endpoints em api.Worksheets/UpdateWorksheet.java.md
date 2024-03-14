# UpdateWorksheet.java
Esta classe do tipo Servlet representa um endpoint da API que tem como objetivo atualizar uma ficha de trabalho

### Como utilizar este endpoint?
- Dependendo da maneira como estiver a correr o projeto, deverá utilizar um dos dois URL's abaixo:
    - Se o projeto estiver a ser corrido localmente, deverá usar o URL <http://localhost:8080/AlgorithmiBO/api/UpdateWorksheet>
    - Se o projeto estiver a ser corrido remotamente, deverá usar o URL <http://ram.ipt.pt:8080/AlgorithmiBO/api/UpdateWorksheet>
- Deverá enviar (em formato **JSON**) no corpo do pedido HTTP os seguintes parâmetros:
    - `"id"`: parâmetro do tipo inteiro. Contém o ID que identifica a ficha de trabalho na base de dados.
    - `"num"`: parâmetro do tipo inteiro. Contém o número da ficha de trabalho.
    - `"title"`: parâmetro do tipo string. Contém o título relacionado da ficha de trabalho.
    - `"image"`: parâmetro do tipo string. Contém a imagem da ficha de trabalho em base64.
    - `"sendDate"`: parâmetro do tipo string. Contém a data de envio da ficha de trabalho.
    - `"problems"`: parâmetro do tipo string. Contém os problemas relacionados à ficha de trabalho.
    - `"date"`: parâmetro do tipo string. Contém a data associada à ficha de trabalho.
    - `"author"`: parâmetro do tipo string. Contém o autor associado à ficha de trabalho.
    - `"courseId"`: parâmetro do tipo string. Contém o ID do curso associado à ficha de trabalho.
    - `"updateUser"`: parâmetro do tipo string. Contém o utilizador responsável pela atualização da ficha de trabalho.
    - `"jwtToken"`: parâmetro do tipo string. Contém o token JWT que autoriza o utilizador a realizar da ficha de trabalho.

### Exemplo de um pedido enviado para este endpoint
```json
{
    "id": 123,
    "num": 456,
    "title": "Título do exemplo",
    "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAIAAAACACAYAAADDPm...",
    "sendDate": "2024-03-14",
    "problems": "Problemas relacionados ao exemplo",
    "date": "username",
    "courseId": "123",
    "updateUser": "username",
    "jwtToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c"
}
```

### Exemplo de uma resposta bem sucedida (código 200)
Se a atualização for feita com sucesso, o servidor devolve código 200.


### Exemplo de uma resposta mal sucedida (código 401 - UNAUTHORIZED)
Se token enviado não for válido, o servidor devolve ```"401 - Token not valid"```. Isto significa que o token ***JWT*** enviado não é válido. Isto pode acontecer em várias situações, como por exemplo, se o token já não existir.