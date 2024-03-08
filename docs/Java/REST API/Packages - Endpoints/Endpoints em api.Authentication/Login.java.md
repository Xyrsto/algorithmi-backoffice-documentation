# Login.java
Esta classe do tipo Servlet representa um endpoint da API que tem como objetivo a autenticação de utilizadores para a nova versão do Algorithmi. 
<br>
Se a autenticação for feita com sucesso, a API devolve um token JWT que deverá ser enviado em todas as requests (exceto Login e Registo). Este token é utilizado para autenticar um utilizador e dar autorização para aceder aos recursos que a API disponibiliza.

### Como utilizar este endpoint?
1. Dependendo da maneira como estiver a correr o projeto, deverá utilizar um dos dois URL's abaixo:
    - Se o projeto estiver a ser corrido localmente, deverá usar o URL <http://localhost:8080/AlgorithmiBO/api/Login>
    - Se o projeto estiver a ser corrido remotamente, deverá usar o URL <http://ram.ipt.pt:8080/AlgorithmiBO/api/Login>
2. Deverá enviar (em formato **JSON**) no corpo do pedido HTTP os seguintes parâmetros:
    - ```"email"```: parâmetro do tipo string. Contém o email do utilizador que se pretende autenticar.  
    - ```"password"```: parâmetro do tipo string. Contém a password do utilizador que se pretende autenticar.
3. O endpoint envia um pedido à base de dados para verificar se os dados recebidos estão registados.
<br><br>
**É importante salientar que no pedido HTTP, os nomes dos parâmetros devem ser exatamente como estão descritos acima.**

### Exemplo de um pedido enviado para este endpoint
```json
{
    "email": "algorithmibackoffice@ipt.pt",
    "password": "teste",
}
```

### Exemplo de uma resposta bem sucedida (código 200 OK)
Se o utilizador estiver registado no sistema, e os dados fornecidos forem corretos, será devolvido um token JWT.
<br> O token mostrado abaixo está incompleto e serve apenas como exemplo.
```json
"eyJraWQiOiIwbHRLaHNUMFhSK1lyV0ZoaElrOWhBUUl6ZzRBOHF4L1IyVHQxekxBUmZZPSIsImFsZyI6IkhTMjU2In0.eyJ1c2VySUQiOjYsInVzZXJGaXJzdE5hbWUiOiJSb2RyaWdvIiwidXNlckxhc3ROYW1lIjoiU2VycmEiLCJ1c2VyVXNlcm5hbWUiOiJyc2VycmEiLCJ1c2VyRW1haWwiOiJhbHVubzI0MTgwQGlwdC5wdCIsInVzZXJJbWFnZSI6ImRhdGE6aW1hZ2UvcG5nO2Jhc2U2NCxpVkJPUncwS0dnb0FBQUFOU1VoRVVnQUFBZG9BQUFIYUNBWUFBQUNuNUlpdkFBQUFCSE5DU1ZRSUNBZ0lmQWhraUFBQUlBQkpSRUZVZUY3c3ZZdDYyN2pTcGUyRGZFaDZ6elAzZnpYL014YzA4L1h1VXhMYmt2LzFyc0lpSVlpVVpNZEpKOTFtSXBNNEZRb0ZvQllLQU1IT...""
```