# Porquê JWT
*** 
## O que é JWT?

JWT, que significa "JSON Web Token", é um padrão aberto (RFC 7519) que define uma forma compacta e autónoma para transmitir informações entre partes como um objeto JSON. Essas informações podem ser verificadas e confiáveis porque são assinadas digitalmente. JWTs podem ser assinados usando um segredo (com o algoritmo HMAC) ou um par de chaves pública/privada usando RSA ou ECDSA.

## Como funciona?

O funcionamento básico de um JWT é simples: ele consiste em três partes separadas por pontos (`.`), que são:

1. **Header**: Contém o tipo de token (que é JWT) e o algoritmo de assinatura utilizado.
2. **Payload**: É onde os dados são armazenados. O payload contém as afirmações (ou como são chamadas normalmente, *claims*), que são declarações sobre uma entidade (geralmente o utilizador) e metadados adicionais.
3. **Assinatura**: Para verificar a integridade do token, é necessária uma assinatura. A assinatura é gerada combinando o header codificado, o payload codificado e uma chave secreta (ou chave pública, no caso de assinatura assimétrica).

## Por que deve ser utilizado para garantir segurança?

JWT é amplamente utilizado para autenticação e autorização em aplicações web e APIs por várias razões:

- **Simplicidade**: O formato compacto de JWT torna-o fácil de ser enviado através de HTTP e armazenado em cookies ou cabeçalhos HTTP.
- **Segurança**: JWTs podem ser assinados e criptografados, garantindo que os dados não sejam adulterados durante a transmissão.
- **Escalabilidade**: JWTs são autocontidos, o que significa que as informações relevantes são incluídas no próprio token, eliminando a necessidade de consultar um banco de dados para verificar as credenciais do utilizador a cada solicitação.
- **Interoperabilidade**: JWTs são baseados em JSON, tornando-os compatíveis com uma ampla variedade de linguagens de programação e frameworks.
- **Desempenho**: Como os JWTs podem ser verificados sem a necessidade de acessar um banco de dados ou servidor de sessão, eles podem melhorar o desempenho de aplicações com grande carga de tráfego.

## Como utilizamos JWT neste projeto?
Cada vez um utilizador se autentica no sistema, é gerado um novo token ***JWT*** e uma chave para o assinar. Essa chave é então guardada na base de dados, juntamente com o ***ID*** da chave, utilizado para a identificar.
<br> 
Sempre que um utilizador pretender utilizar um endpoint da ***API***, este terá de estar autenticado no sistema, pois só assim terá um token JWT válido para ser enviado. O utilizador só terá acesso ao conteúdo do endpoint, se o token ***JWT*** enviado for verificado, isto é, se a chave criada no momento da autenticação conseguir descompactar este token.
<br>
Dentro de cada token vão todos os dados relevantes para o utilizador autenticado no sistema, podendo estes ser utilizados em qualquer parte do frontend, visto que o token é guardado na ***localStorage*** do browser.
