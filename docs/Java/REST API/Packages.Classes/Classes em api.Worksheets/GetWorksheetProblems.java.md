# GetWorksheetProblems.java
Esta classe do tipo Servlet representa um endpoint da API que tem como objetivo obter todos os problemas associados a uma folha de exercícios da base de dados.

### Como utilizar este endpoint?
1. Dependendo da maneira como estiver a correr o projeto, deverá utilizar um dos dois URL's abaixo:
    - Se o projeto estiver a ser corrido localmente, deverá usar o URL <http://localhost:8080/api/GetWorksheetProblems>
    - Se o projeto estiver a ser corrido remotamente, deverá usar o URL <http://ram.ipt.pt:8080/api/GetWorksheetProblems>
2. Deverá enviar (em formato **JSON**) no corpo do pedido HTTP os seguintes parâmetros:
    - `"id"`: parâmetro do tipo int. Contém o ID da ficha de exercícios da qual deseja obter os problemas.
    - `"jwtToken"`: parâmetro do tipo string. Contém o token JWT que autoriza o utilizador a realizar a operação.
3. O endpoint retorna uma lista de problemas associados à folha de exercícios se o token JWT for válido e se o ID da folha de exercícios existir na base de dados.

### Exemplo de um pedido enviado para este endpoint
```json
{
    "id": 1,
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
        "image": "data:image/png;base64,/9j/4AAQSkZJRgABAgAAAQABAAD/2wBDAAEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQICAQECAQEBAgICAgICAgICAQICAgICAgICAgL/2wBDAQEBAQEBAQEBAQECAQEBAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgL/wAARCAA6AHYDASIAAhEBAxEB/8QAHwAAAQUBAQEBAQEAAAAAAAAAAAECAwQFBgcICQoL/8QAtRAAAgEDAwIEAwUFBAQAAAF9AQIDAAQRBRIhMUEGE1FhByJxFDKBkaEII0KxwRVS0fAkM2JyggkKFhcYGRolJicoKSo0NTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uHi4+Tl5ufo6erx8vP09fb3+Pn6/8QAHwEAAwEBAQEBAQEBAQAAAAAAAAECAwQFBgcICQoL/8QAtREAAgECBAQDBAcFBAQAAQJ3AAECAxEEBSExBhJBUQdhcRMiMoEIFEKRobHBCSMzUvAVYnLRChYkNOEl8RcYGRomJygpKjU2Nzg5OkNERUZHSElKU1RVVldYWVpjZGVmZ2hpanN0dXZ3eHl6goOEhYaHiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU1dbX2Nna4uPk5ebn6Onq8vP09fb3+Pn6/9oADAMBAAIRAxEAPwD8Zv8Ag4i/5E//AIJx/wDZNP2k/wD1ektfzfx+CfGc3g+4+IUXhHxPL4BtNfj8KXXjiPQNVfwfbeKJrIanD4buPEq2hsodffTSLhbNpxcNARKIzH81f0gf8HEX/In/APBOP/smn7Sf/q9Ja/A2zvdKH7OGsae37QXiey1p/i5ZXUf7L8ei+M38H61pw8LpG3xnuPEEWpjQItfgnzpK2stm2qGCMSJOLbCV2+ImNxGC4ixDw0Od4rMaFGf+z4rEWp1WozlbC06jo2X/ADEV+TC0vir1IR1PiqeYYvLsj4clhKftHjMXhsPU/wBlxuKtSrVpRqStgqVZ0LLX61iVTwVD4sTVpw1PMfC/gnxn44n1e18FeEfE/jC50DQNS8V67b+F9A1XxBPonhfRRE2seJNXi0m0mbTdAtFngNzeTBLeATIZZE3DORpOk6rr+q6ZoWhaZqGta3rWoWWk6No2k2VzqOq6tquo3Mdnp+maZp9nG81/...",
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
            "": "\/"
        },
        "difficulty": 1,
        "id": 6,
        "language": 1,
        "author": "ana",
        "date": "16/05/2022",
        "descript": "<p style=\\\"text-align: center;\\\"><strong><span style=\\\"color: rgbrgb(65, 168, 95); font-size: 18px;\\\">Construa um algoritmo que imprima na consola o seguinte texto:</span></strong></p>",
        "image": "data:image/png;base64,/9j/4AAQSkZJRgABAgAAAQABAAD/2wBDAAEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQICAQECAQEBAgICAgICAgICAQICAgICAgICAgL/2wBDAQEBAQEBAQEBAQECAQEBAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgL/wAARCAA7ACcDASIAAhEBAxEB/8QAHwAAAQUBAQEBAQEAAAAAAAAAAAECAwQFBgcICQoL/8QAtRAAAgEDAwIEAwUFBAQAAAF9AQIDAAQRBRIhMUEGE1FhByJxFDKBkaEII0KxwRVS0fAkM2JyggkKFhcYGRolJicoKSo0NTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqDhIWGh4iJipKTlJWWl5iZmqKjpKWmp6ipqrKztLW2t7i5usLDxMXGx8jJytLT1NXW19jZ2uHi4+Tl5ufo6erx8vP09fb3+Pn6/8QAHwEAAwEBAQEBAQEBAQAAAAAAAAECAwQFBgcICQoL/...",
        "solver": "rO0ABXNyABtmbG93Y2hhcnQuYWxnb3JpdGhtLlByb2dyYW0AAAAu6uBpbwIADVoAGGNvbXBhY3RlZENvZGVUcmFuc2xhdGlvbkkAC2hlYWRlckxpbmVzWgAJaXNEZWxldGVkWgANaXNTYXZlZEluRmlsZUwACWNsaXBib2FyZHQAKkxmbG93Y2hhcnQvYWxnb3JpdGhtL2NsaXBCb2FyZC9GY2xpcEJvYXJkO0wAEGNvbXBpbGF0aW9uX2xvY2t0ACFMamF2YS91dGlsL2NvbmN1cnJlbnQvbG9ja3MvTG9jaztMAAhmaWxlTmFtZXQAEkxqYXZhL2xhbmcvU3RyaW5nO0wACWZ1bmN0aW9uc3QAEExqYXZhL3V0aWwvTGlzdDtMAAlnbG9iYWxNZW10ACdMZmxvd2NoYXJ0L2FsZ29yaXRobS9HbG9iYWxNZW1vcnlHcmFwaDtMAARtYWludAAkTGZsb3djaGFydC9hbGdvcml0aG0vQWxnb3JpdGhtR3JhcGg7TAAJbXlQcm9ibGVtdAAdTGZsb3djaGFydC9hbGdvcml0aG0vUHJvYmxlbTtMAAp0cmFuc2xhdG9ydAAYTGkxOG4vdXRpbHMvRlRyYW5zbGF0b3I7TAAOdmFyaWFibGVQcmVmaXhxAH4AA3hwAAAAAAAAAHBzcgAoamF2YS51dGlsLmNvbmN1cnJlbnQubG9ja3MuUmVlbnRyYW50TG9ja2ZVqCwsyGrrAgABTAAEc3luY3QAL0xqYXZhL3V0aWwvY29uY3VycmVudC9sb2Nrcy9SZWVudHJhbnRMb2NrJFN5bmM7eHBzcgA0amF2YS51dGlsLmNvbmN1cnJlbnQubG9ja3MuUmVlbnRyYW50TG9jayROb25mYWlyU3luY2WIMudTe78LAgAAeHIALWphdmEudXRpbC5jb25jdXJyZW50LmxvY2tzLlJlZW50cmFudExvY2skU3luY7geopSqRFp8AgAAeHIANWphdmEudXRpbC5jb25jdXJyZW50LmxvY2tzLkFic3RyYWN0UXVldWVkU3luY2hyb25pemVyZlWoQ3U/UuMCAAFJAAVzdGF0ZXhyADZqYXZhLnV0aWwuY29uY3VycmVudC5sb2Nrcy5BYnN0cmFjdE93bmFibGVTeW5jaHJvbml6ZXIz36+5rW1vqQIAAHhwAAAAAHQAEEZpY2hhMDFfMDA2LnByb2dzcgATamF2YS51dGlsLkFycmF5TGlzdHiB0h2Zx2GdAwABSQAEc2l6ZXhwAAAAAHcEAAAAAHhwc3IAImZsb3djaGFydC5hbGdvcml0aG0uQWxnb3JpdGhtR3JhcGgAAAAu6uBpbwIAB1oABmlzTWFpbkkACmxpbmVOdW1iZXJMAAVncmFwaHQAFExqYXZheC9zd2luZy9KUGFuZWw7TAANbXlMb2NhbE1lbW9yeXQADUxjb3JlL01lbW9yeTtMAARuYW1lcQB...",
        "tags": null,
        "title": "Barra \\\\",
        "updateauthor": null,
        "updatedate": null,
        "videolink": "https://www.youtube.com/embed/Zm6FxXUwKdM",
        "code": null,
        "userEfficacy": 0.0,
        "userEfficiency": 0.0,
        "userOriginality": 0.0
    },
    ...
]
```

### Exemplo de uma resposta mal sucedida (código 401 - UNAUTHORIZED)
Se token enviado não for válido, o servidor devolve ```"401 - Token not valid"```. Isto significa que o token ***JWT*** enviado não é válido. Isto pode acontecer em várias situações, como por exemplo, se o token já não existir.