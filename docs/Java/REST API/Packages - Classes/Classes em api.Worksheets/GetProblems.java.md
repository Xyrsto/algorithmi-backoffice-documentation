# GetProblems.java
Esta classe do tipo Servlet representa um endpoint da API que tem como objetivo obter toda a lista de problemas da base de dados.
<br>
Ao receber um pedido HTTP, este endpoint verifica a validade do token JWT fornecido no corpo do pedido para garantir a autorização do utilizador.

### Como utilizar este endpoint?
1. Dependendo da maneira como estiver a correr o projeto, deverá utilizar um dos dois URL's abaixo:
    - Se o projeto estiver a ser corrido localmente, deverá usar o URL <http://localhost:8080/api/GetProblems>
    - Se o projeto estiver a ser corrido remotamente, deverá usar o URL <http://ram.ipt.pt:8080/api/GetProblems>
2. Deverá enviar (em formato **JSON**) no corpo do pedido HTTP os seguintes parâmetros:
    - `"jwtToken"`: parâmetro do tipo string. Contém o token JWT que autoriza o utilizador a realizar a operação.
3. O endpoint retorna uma lista de problemas da base de dados se o token JWT for válido.

### Exemplo de um pedido enviado para este endpoint
```json
{
    "jwtToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c..."
}
```

### Exemplo de uma resposta bem sucedida (código 200 OK)
```json
[
    {
        "point": 1.0,
        "inputs": {
            "": "Olá Mundo"
        },
        "difficulty": 1,
        "id": 1,
        "language": 1,
        "author": "ana",
        "date": "16/05/2022",
        "descript": "<p style=\\\"text-align: center;\\\"><strong><span style=\\\"color: rgbrgb(65, 168, 95); font-size: 18px;\\\">Construa um algoritmo que imprima na consola a mensagem:\r\nOlá Mundo</span></strong></p>",
        "solver": "rO0ABXNyABtmbG93Y2hhcnQuYWxnb3JpdGhtLlByb2dyYW0AAAAu6uBpbwIADVoAGGNvbXBhY3RlZENvZGVUcmFuc2xhdGlvbkkAC2hlYWRlckxpbmVzWgAJaXNEZWxldGVkWgANaXNTYXZlZEluRmlsZUwACWNsaXBib2FyZHQAKkxmbG93Y2hhcnQvYWxnb3JpdGhtL2NsaXBCb2FyZC9GY2xpcEJvYXJkO0wAEGNvbXBpbGF0aW9uX2xvY2t0ACFMamF2YS91dGlsL2NvbmN1cnJlbnQvbG9ja3MvTG9jaztMAAhmaWxlTmFtZXQAEkxqYXZhL2xhbmcvU3RyaW5nO0wACWZ1bmN0aW9uc3QAEExqYXZhL3V0aWwvTGlzdDtMAAlnbG9iYWxNZW10ACdMZmxvd2NoYXJ0L2FsZ29yaXRobS9HbG9iYWxNZW1vcnlHcmFwaDtMAARtYWludAAkTGZsb3djaGFydC9hbGdvcml0aG0vQWxnb3JpdGhtR3JhcGg7TAAJbXlQcm9ibGVtdAAdTGZsb3djaGFydC9hbGdvcml0aG0vUHJvYmxlbTtMAAp0cmFuc2xhdG9ydAAYTGkxOG4vdXRpbHMvRlRyYW5zbGF0b3I7TAAOdmFyaWFibGVQcmVmaXhxAH4AA3hwAAAAAAAAAHBzcgAoamF2YS51dGlsLmNvbmN1cnJlbnQubG9ja3MuUmVlbnRyYW50TG9ja2ZVqCwsyGrrAgABTAAEc3luY3QAL0xqYXZhL3V0aWwvY29uY3VycmVudC9sb2Nrcy9SZWVudHJhbnRMb2NrJFN5bmM7eHBzcgA0amF2YS51dGlsLmNvbmN1cnJlbnQubG9ja3MuUmVlbnRyYW50TG9jayROb25mYWlyU3luY2WIMudTe78LAgAAeHIALWphdmEudXRpbC5jb25jdXJyZW50LmxvY2tzLlJlZW50cmFudExvY2skU3luY7geopSqRFp8AgAAeHIANWphdmEudXRpbC5jb25jdXJyZW50LmxvY2tzLkFic3RyYWN0UXVldWVkU3luY2hyb25pemVyZlWoQ3U/UuMCAAFJAAVzdGF0ZXhyADZqYXZhLnV0aWwuY29uY3VycmVudC5sb2Nrcy5BYnN0cmFjdE93bmFibGVTeW5jaHJvbml6ZXIz36+5rW1vqQIAAHhwAAAAAHQAEEZpY2hhMDFfMDAxLnByb2dzcgATamF2YS51dGlsLkFycmF5TGlzdHiB0h2Zx2GdAwABSQAEc2l6ZXhwAAAAAHcEAAAAAHhwc3IAImZsb3djaGFydC5hbGdvcml0aG0uQWxnb3JpdGhtR3JhcGgAAAAu6uBpbwIAB1oABmlzTWFpbkkACmxpbmVOdW1iZXJMAAVncmFwaHQAFExqYXZheC9zd2luZy9KUGFuZWw7TAANbXlMb2NhbE1lbW9yeXQADUxjb3JlL01lbW9yeTtMAARuYW1lcQB...",
        "tags": null,
        "title": "Olá Mundo",
        "updateauthor": null,
        "updatedate": null,
        "videolink": "https://www.youtube.com/embed/xG2G_V2MWno",
        "code": null,
        "userEfficacy": 0.0,
        "userEfficiency": 0.0,
        "userOriginality": 0.0
    },
    {
        "point": 1.0,
        "inputs": {
            "": "Olá Mundo"
        },
        "difficulty": 1,
        "id": 2,
        "language": 1,
        "author": "ana",
        "date": "16/05/2022",
        "descript": "<p style=\\\"text-align: center;\\\"><strong><span style=\\\"color: rgbrgb(65, 168, 95); font-size: 18px;\\\">Construa um algoritmo que imprima na consola a mensagem:\r\nOlá Mundo</span></strong></p>",
        "solver": "rO0ABXNyABtmbG93Y2hhcnQuYWxnb3JpdGhtLlByb2dyYW0AAAAu6uBpbwIADVoAGGNvbXBhY3RlZENvZGVUcmFuc2xhdGlvbkkAC2hlYWRlckxpbmVzWgAJaXNEZWxldGVkWgANaXNTYXZlZEluRmlsZUwACWNsaXBib2FyZHQAKkxmbG93Y2hhcnQvYWxnb3JpdGhtL2NsaXBCb2FyZC9GY2xpcEJvYXJkO0wAEGNvbXBpbGF0aW9uX2xvY2t0ACFMamF2YS91dGlsL2NvbmN1cnJlbnQvbG9ja3MvTG9jaztMAAhmaWxlTmFtZXQAEkxqYXZhL2xhbmcvU3RyaW5nO0wACWZ1bmN0aW9uc3QAEExqYXZhL3V0aWwvTGlzdDtMAAlnbG9iYWxNZW10ACdMZmxvd2NoYXJ0L2FsZ29yaXRobS9HbG9iYWxNZW1vcnlHcmFwaDtMAARtYWludAAkTGZsb3djaGFydC9hbGdvcml0aG0vQWxnb3JpdGhtR3JhcGg7TAAJbXlQcm9ibGVtdAAdTGZsb3djaGFydC9hbGdvcml0aG0vUHJvYmxlbTtMAAp0cmFuc2xhdG9ydAAYTGkxOG4vdXRpbHMvRlRyYW5zbGF0b3I7TAAOdmFyaWFibGVQcmVmaXhxAH4AA3hwAAAAAAAAAHBzcgAoamF2YS51dGlsLmNvbmN1cnJlbnQubG9ja3MuUmVlbnRyYW50TG9ja2ZVqCwsyGrrAgABTAAEc3luY3QAL0xqYXZhL3V0aWwvY29uY3VycmVudC9sb2Nrcy9SZWVudHJhbnRMb2NrJFN5bmM7eHBzcgA0amF2YS51dGlsLmNvbmN1cnJlbnQubG9ja3MuUmVlbnRyYW50TG9jayROb25mYWlyU3luY2WIMudTe78LAgAAeHIALWphdmEudXRpbC5jb25jdXJyZW50LmxvY2tzLlJlZW50cmFudExvY2skU3luY7geopSqRFp8AgAAeHIANWphdmEudXRpb...,
        "tags": null,
        "title": "Olá Mundo",
        "updateauthor": null,
        "updatedate": null,
        "videolink": "https://www.youtube.com/embed/RgdT6naYs7s",
        "code": null,
        "userEfficacy": 0.0,
        "userEfficiency": 0.0,
        "userOriginality": 0.0
    }
    ...
]
```

### Exemplo de uma resposta mal sucedida (código 401 - UNAUTHORIZED)
Se token enviado não for válido, o servidor devolve ```"401 - Token not valid"```. Isto significa que o token ***JWT*** enviado não é válido. Isto pode acontecer em várias situações, como por exemplo, se o token já não existir.