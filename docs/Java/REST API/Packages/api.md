# api
*** 
Package com classes que representam endpoints com finalidade genérica na API.

## LanguagesAPI.java
Esta classe do tipo Servlet representa um endpoints da API que tem como objetivo a tradução do código escrito no **Algorithmi** para diversas linguagens de programação.

### Como utilizar este endpoint?
1. Dependendo da maneira como estiver a correr o projeto, deverá utilizar um dos dois URL's abaixo:
    - Se o projeto estiver a ser corrido localmente, deverá usar o URL <http://localhost:8080/AlgorithmiBO/api/LanguagesAPI>
    - Se o projeto estiver a ser corrido remotamente, deverá usar o URL <http://ram.ipt.pt:8080/AlgorithmiBO/api/LanguagesAPI>
2. Deverá enviar (em formato **JSON**) no corpo do pedido HTTP os seguintes parâmetros:
    - ```"program"```: parâmetro do tipo string. Deverá conter o código do programa    
    - ```"jwtToken"```: parâmetro do tipo string. Deve conter o token JWT para autenticação e autorização.
    - ```"language"```: parâmetro do tipo string. Deve conter a linguagem para a qual o código será traduzido.

### Linguagens suportadas

- **"c#"** : traduz o código para C#
- **"c++"** : traduz o código para C++
- **"javascript - html - css"**" : traduz o código para uma página HTML com JavaScript e CSS
- **"java"** : traduz o código para Java
- **"c language c11"** : traduz o código para um standard antigo de C (ISO/IEC 9899:2011)
- **"python 3"** : traduz o código para Python 3
- **"php 5.3 +"** : traduz o código para PHP 5.3
- **"javascript"** : traduz o código para JavaScript
- **"algorithmi"** : traduz o código para a linguagem Algorithmi
<br><br>
**É importante salientar que deve ser enviado no pedido HTTP os nomes da linguagens exatamente como estão descritas acima.**

### Exemplo de um pedido enviado para este endpoint
```json
{
    "program": "begin MainProgram\n\t\nend MainProgram",
    "jwtToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJz...",
    "language": "c language c11"
}
```

### Exemplo de uma resposta bem sucedida (código 202 - Accepted)
```C
// Programmer           Algorithmi - My_Full_Name

#include <stdio.h>
#include <string.h>
#include <math.h>
//Main Function
int main() {
    return 0;
}
```
