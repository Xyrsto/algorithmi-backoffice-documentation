# InsertProblem.java
Esta classe do tipo Servlet representa um endpoint da API que tem como objetivo inserir um novo problema na base de dados.

### Como utilizar este endpoint?
1. Dependendo da maneira como estiver a correr o projeto, deverá utilizar um dos dois URL's abaixo:
    - Se o projeto estiver a ser corrido localmente, deverá usar o URL <http://localhost:8080/api/InsertProblem>
    - Se o projeto estiver a ser corrido remotamente, deverá usar o URL <http://ram.ipt.pt:8080/api/InsertProblem>
2. Deverá enviar (em formato **JSON**) no corpo do pedido HTTP os seguintes parâmetros:
    - `"problemTitle"`: Parâmetro do tipo string. Representa o título do problema
    - `"problemDescription"`: Parâmetro do tipo string. Descreve o problema em detalhe
    - `"problemPoints"`: Parâmetro do tipo string. Indica o número de pontos atribuídos ao problema
    - `"problemVideoURL"`: Parâmetro do tipo string. Contém o URL do vídeo relacionado ao problema
    - `"base64String"`: Parâmetro do tipo string. Contém uma representação em base64 da imagem do problema.
    - `"allTags"`: Parâmetro do tipo string. Fornece as tags associadas ao problema
    - `"difficultyId"`: Parâmetro do tipo string. Identifica o nível de dificuldade do problema
    - `"languageId"`: Parâmetro do tipo string. Identifica a linguagem de programação associada ao problema
    - `"allInputs"`: Parâmetro do tipo string. Contém uma lista de entradas para o problema
    - `"allOutputs"`: Parâmetro do tipo string. Contém uma lista de saídas esperadas para as entradas fornecidas
    - `"solverString"`: Parâmetro do tipo string. Contém o código do solver associado ao problema
    - `"author"`: Parâmetro do tipo string. Indica o autor do problema
    - `"jwtToken"`: Parâmetro do tipo string. Contém o token JWT que autoriza o utilizador a realizar a operação

    
3. O endpoint retorna uma mensagem de sucesso se o problema for inserido com sucesso na base de dados.

### Exemplo de um pedido enviado para este endpoint

```json
{
    To be continued after frontend bug is fixed
}
```
