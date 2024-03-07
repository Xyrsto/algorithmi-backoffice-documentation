# Register.java
Esta classe do tipo Servlet representa um endpoint da API que tem como objetivo o registo de utilizadores para a nova versão do Algorithmi.
<br>

### Como utilizar este endpoint?
1. Dependendo da maneira como estiver a correr o projeto, deverá utilizar um dos dois URL's abaixo:
    - Se o projeto estiver a ser corrido localmente, deverá usar o URL <http://localhost:8080/AlgorithmiBO/api/Register>
    - Se o projeto estiver a ser corrido remotamente, deverá usar o URL <http://ram.ipt.pt:8080/AlgorithmiBO/api/Register>
2. Deverá enviar (em formato **JSON**) no corpo do pedido HTTP os seguintes parâmetros:
    - `"username"`: parâmetro do tipo string. Contém o nome de utilizador desejado para o novo utilizador.
    - `"email"`: parâmetro do tipo string. Contém o email do novo utilizador.
    - `"password"`: parâmetro do tipo string. Contém a password do novo utilizador.
    - `"firstName"`: parâmetro do tipo string. Contém o primeiro nome do novo utilizador.
    - `"lastName"`: parâmetro do tipo string. Contém o último nome do novo utilizador.
    - `"image"`: parâmetro do tipo string. Contém uma string Base64 da imagem de perfil do novo utilizador.
    - `"course"`: parâmetro do tipo int. Contém o identificador do curso do novo utilizador.
        - Para **Instituto politécnico de Tomar**: deverá enviar ```"1"```
        - Para **External**: deverá enviar ```"2"```.
    - `"language"`: parâmetro do tipo int. Contém o identificador do idioma preferido do novo utilizador.
        - Para **português**: deverá enviar ```"1"```
        - Para **inglês**: deverá enviar ```"2"```
3. O endpoint cria uma nova conta de utilizador na base de dados com os dados fornecidos.
<br><br>
**É importante salientar que no pedido HTTP, os nomes dos parâmetros devem ser exatamente como estão descritos acima.**

### Exemplo de um pedido enviado para este endpoint
```json
{
    "username": "novo_utilizador",
    "email": "novo_utilizador@example.com",
    "password": "nova_password",
    "firstName": "Novo",
    "lastName": "Utilizador",
    "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAAAXNSR0IA5...",
    "course": 2,
    "language": 1
}
```

### Exemplo de uma resposta bem sucedida (código 200 OK)
Se o registo for efetuado com sucesso, o servidor responde com código 200 OK.
