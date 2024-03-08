# GetCourses.java
Esta classe do tipo Servlet representa um endpoint da API que tem como objetivo obter a lista de todos os cursos da base de dados.
<br>
Ao receber um pedido HTTP, este endpoint verifica a validade do token JWT fornecido no corpo do pedido para garantir a autorização do utilizador.

### Como utilizar este endpoint?
1. Dependendo da maneira como estiver a correr o projeto, deverá utilizar um dos dois URL's abaixo:
    - Se o projeto estiver a ser corrido localmente, deverá usar o URL <http://localhost:8080/api/GetCourses>
    - Se o projeto estiver a ser corrido remotamente, deverá usar o URL <http://ram.ipt.pt:8080/api/GetCourses>
2. Deverá enviar (em formato **JSON**) no corpo do pedido HTTP os seguintes parâmetros:
    - `"jwtToken"`: parâmetro do tipo string. Contém o token JWT que autoriza o utilizador a realizar a operação.
3. O endpoint retorna a lista de cursos disponíveis na base de dados se o token JWT for válido.

### Exemplo de um pedido enviado para este endpoint
```json
{
    "jwtToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c..."
}
```

### Exemplo de uma resposta bem sucedida (código 200 OK)
Se o token for válido, o servidor devolve 200 OK juntamente com a lista de cursos em formato JSON.
```json
[
    {"id":1,"code":"IPT","desc":"Instituto Politecnico de Tomar"},
    {"id":2,"code":"EXT","desc":"External"}
]
```

### Exemplo de uma resposta mal sucedida (código 401 - UNAUTHORIZED)
Se token enviado não for válido, o servidor devolve ```"401 - Token not valid"```. Isto significa que o token ***JWT*** enviado não é válido. Isto pode acontecer em várias situações, como por exemplo, se o token já não existir.
