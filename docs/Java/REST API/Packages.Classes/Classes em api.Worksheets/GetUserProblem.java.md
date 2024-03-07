# GetUserProblem.java
Esta classe do tipo Servlet representa um endpoint da API que tem como objetivo obter detalhes sobre um problema específico de um utilizador.
<br>
Ao receber um pedido HTTP, este endpoint verifica a validade do token JWT fornecido no corpo do pedido para garantir a autorização do utilizador.

### Como utilizar este endpoint?
1. Dependendo da maneira como estiver a correr o projeto, deverá utilizar um dos dois URL's abaixo:
    - Se o projeto estiver a ser corrido localmente, deverá usar o URL <http://localhost:8080/api/GetUserProblem>
    - Se o projeto estiver a ser corrido remotamente, deverá usar o URL <http://ram.ipt.pt:8080/api/GetUserProblem>
2. Deverá enviar (em formato **JSON**) no corpo do pedido HTTP os seguintes parâmetros:
    - `"id"`: parâmetro do tipo inteiro. Contém o ID do problema que o utilizador deseja obter detalhes.
    - `"jwtToken"`: parâmetro do tipo string. Contém o token JWT que autoriza o utilizador a realizar a operação.
   
3. O endpoint retorna os detalhes do problema para o utilizador, incluindo título, descrição, pontos, vídeo relacionado, código do problema, eficácia do utilizador, eficiência do utilizador e originalidade do utilizador.

### Exemplo de um pedido enviado para este endpoint
```json
{
    "id": 123,
    "jwtToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c...",   
}
```

### Exemplo de uma resposta bem sucedida (código 200 OK)
```json
{
    "point": 3.0,
    "inputs": {
        "": "\\     /break \\   /break  \\ /break\"\"\"V\"\"\""
    },
    "difficulty": 3,
    "id": 7,
    "language": 1,
    "author": "username",
    "date": "16/05/2022",
    "descript": "<p style=\\\"text-align: center;\\\"><strong><span style=\\\"color: rgbrgb(65, 168, 95); font-size: 18px;\\\">Construa um algoritmo que imprima na consola o seguinte texto:</span></strong></p>",
    "image": "data:image/png;base64,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...",
    "solver": "    begin MainProgram\n        write \"\\\\     /\\n\"\n        write \" \\\\   /\\n\"\n        write \"  \\\\ /\\n\"\n        write \"\\\"\\\"\\\"V\\\"\\\"\\\"\"\n    end MainProgram\n\n",
    "tags": null,
    "title": "V de Vitória",
    "updateauthor": null,
    "updatedate": null,
    "videolink": "",
    "code": "begin MainProgram\\n\\tTeste\\n\rendMainProgram",
    "userEfficacy": 0.0,
    "userEfficiency": 0.0,
    "userOriginality": 0.0
}
```

### Variações na resposta bem sucedida
- Se existir na base de dados um problema na tabela **"user_evaluation** com o par ***problemID + userEmail***, o servidor responde com o problema inteiro, e no campo **"code"** do JSON recebido está o código escrito pelo aluno
- Se a dificuldade do problema pedido foi **"Demonstração"**, o servidor responde com o problema inteiro, e no campo **"code"** está o conteúdo do campo **"solver"** 
- Senão, o servidor responde com o programa inteiro, e no campo **"code"** está ***"begin MainProgram\n\t\nendMainProgram"***

### Exemplo de uma resposta mal sucedida (código 401 - UNAUTHORIZED)
Se token enviado não for válido, o servidor devolve ```"401 - Token not valid"```. Isto significa que o token ***JWT*** enviado não é válido. Isto pode acontecer em várias situações, como por exemplo, se o token já não existir.