# Endpoints
***

## Estrutura do projeto
Neste projeto foram criadas várias packages, de modo a organizar os endpoints da API de acordo com a sua finalidade:

### Packages
- ["api"](./Packages/api.md): nesta package estão as classes que representam endpoints com finalidades genéricas (ou seja, que não se associam com nada em particular dentro do Backoffice)
- ["api.Authentication"](./Packages/api.Authentication.md): nesta package estão as classes que representam endpoints relacionados ao registo e à autenticação de utilizadores
- ["api.Worksheets"](./Packages/api.Worksheets.md): nesta package estão as classes que representam endpoints relacionados às fichas de trabalho e aos problemas que constam no **Algorithmi**. 
- ["myUtils"](./Packages/myUtils.md): nesta package estão as classes que contém métodos utilizados em vários endpoints da API.
<br><br>
Se quiser saber mais informações sobre cada uma destas packages, clique no nome de uma delas para ser redirecionado para a sua página.
<br>Antes de continuar a ler sobre cada endpoint, é importante compreender o que são tokens [JWT](./JWT/Porquê%20JWT.md).
