# InsertWorksheet.java
Esta classe do tipo Servlet representa um endpoint da API que tem como objetivo inserir uma nova ficha de exercícios na base de dados.

### Como utilizar este endpoint?
1. Dependendo da maneira como estiver a correr o projeto, deverá utilizar um dos dois URL's abaixo:
    - Se o projeto estiver a ser corrido localmente, deverá usar o URL <http://localhost:8080/api/InsertWorksheet>
    - Se o projeto estiver a ser corrido remotamente, deverá usar o URL <http://ram.ipt.pt:8080/api/InsertWorksheet>

2. Deverá enviar (em formato **JSON**) no corpo do pedido HTTP os seguintes parâmetros:
    - `"num"`: parâmetro do tipo int. Contém o número da nova ficha de exercícios.
    - `"title"`: parâmetro do tipo string. Contém o título da nova ficha de exercícios.
    - `"image"`: parâmetro do tipo string. Contém o caminho para a imagem associada à nova ficha de exercícios.
    - `"sendDate"`: parâmetro do tipo string. Contém a data de envio da nova ficha de exercícios.
    - `"problems"`: parâmetro do tipo string. Contém uma lista de problemas associados à nova ficha de exercícios, separados por vírgula.
    - `"date"`: parâmetro do tipo string. Contém a data de criação da nova ficha de exercícios.
    - `"author"`: parâmetro do tipo string. Contém o autor da nova ficha de exercícios.
    - `"courseId"`: parâmetro do tipo int. Contém o ID do curso associado à nova ficha de exercícios.
    - `"jwtToken"`: parâmetro do tipo string. Contém o token JWT que autoriza o utilizador a realizar a operação.

3. O endpoint retorna uma resposta vazia se a nova ficha de exercícios for inserida com sucesso na base de dados.

### Exemplo de um pedido enviado para este endpoint
```json
{
    "num": 123456,
    "title": "Hello docs!",
    "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAdoAAAHaCAYAAACn5IivAAAABHNCSVQICAgIfAhkiAAAIABJREFUeF7svYt627jSpe2DfEh6zzP3fzX/Mxc08/XuUxLbkv/1rsIiIYiUZMdJJ91mIpM4FQoFoBYKAMHL//N//r/ni3/wtd1uXbrn5/1iXl5eLvpHFBV6cZF41xfxKVqhN9KJ/07Reb66uqp8OhknTfgiXtJxd/jlboW/49U18dWipfzFRfG02+2cn/lTufq84587cUc+E4b/5uLm4vb21r/NZnNxcX3l++2dfvK7//DBMsCP+9X1ZcmEZ2TT6Hfi2aur8NaH98+9LIvRuZ5wR/562itnaBykHzIa66oP3l4gQ/3dz3KPQi/b0OKe33Nrn0O2k3PmfznGpfLfv1LTzXeVudYuF8LHMo8ymur/+apVXy+A1n4vWru5CH9pc5IXbU/h3HfbfeGN9U35R7/efa32tHTtLud+4vjqT86vtfuZxiCvgRhlP5a/CDrFGhX6V39dtvjxG91jWdL/8O/bjeuk6bCLq2pPxEHvuJ9trn2/vK47bvogv2v5XaqfQmPs/yI6sbBXdtX10rXQfVu0ik9eXM8w1l2R6XNrH33ZKlq1n1lXtXZDXS5caaMjnd4/yci7r9OJl4E2aaM/SbtEa6l/9vTyLM34776WBGWhNrEgKAt4uX4PhNc3zlRMH+mY35QX+acTHeSw79E3GPM9KIaJTmtES/FJt+Y/0hvZcWdWnvnR+XmOf3jq7z2N8Nfn3+e5Vj+hMfI98jeHzxU4yWSMvOBeoj/5WdfxZyFh80rctTzX/EOxV7RLuazgzFLUs/xGfkZ3iFQdpZ0uCyBxjmUc+qOc1toDtIrumR3yWOaN1okoB/n1+Yf/ZQmI8gk2CV5Ne4oxyA/Nr6+vtbobyX6NPD24XrwKaOf2O5dy7FPkv8br7L+ePtmv0SB8zDN+yXspnDhL8uz9SLeU70hvM3osyuwn9kQIEUbKGsFEyEvFO9X4Qzdpe3fRrZClSujzG9O9tD5Cv09nv4WR30g7aZd47BvQUviSzEa/kkNJcsxrpDmWY4w/0l53n6q59ZTHQkbZEbdkdCzVIShEJmP5j1P59qEjP2v1EU7m9oG8l2R+6Fc049/utNUzLtIetPEz0iXNzpY7v3EG4AwipFzLf6GfnUdxjnUUizv5jPHWJJc2Rg59exvr+BifY/0v6RPSnxoIjnks9aPESZ4l6zHl7O7L0espYoxlH8OJc4yHkZfR3fMYWn0eI+3EXxuOzKX6BzxVxe2PPA4a0hnl7OmMAiV53wDO1B+u9NDqaS7RP8ZieFtrGGNHmXhV7x3z7fkZ6fb0w3t/Tz6kW...",
    "sendDate": "2024-03-11",
    "problems": "1,2,3",
    "date": "2024-03-08 15:32",	
	"author": "username",
	"courseId": 1,	
	"jwtToken": "eyJraWQiOiIwbHRLaHNUMFhSK1lyV0ZoaElrOWhBUUl6ZzRBOHF4L1IyVHQxekxBUmZZPSIsImFsZyI6IkhTMjU2In0.eyJ1c2VySUQiOjYsInVzZXJGaXJzdE5hbWUiOiJSb2RyaWdvIiwidXNlckxhc3ROYW1lIjoiU2VycmEiLCJ1c2VyVXNlcm5hbWUiOiJyc2VycmEiLCJ1c2VyRW1haWwiOiJhbHVubzI0MTgwQGlwdC5wdCIsInVzZXJJbWFnZSI6ImRhdGE6aW1hZ2UvcG5nO2Jhc2U2NCxpVkJPUncwS0dnb0FBQUFOU1VoRVVnQUFBZG9BQUFIYUNBWUFBQUNuNUlpdkFBQUFCSE5DU1ZRSUNBZ0lmQWhraUFBQUlBQkpSRUZVZUY3c3ZZdDYyN2pTcGUyRGZFaDZ6elAzZnpYL014YzA4L1h1VXhMYmt2LzFyc0lpSVlpVVpNZEpKOTFtSXBNNEZRb0ZvQllLQU1ITC8vTi8vci9uaTMvd3RkMXVYYnJuNS8xaVhsNWVMdnBIRkJWNmNaRjQxeGZ4S1ZxaE45S0ovMDdSZWI2NnVxcDhPaGtuVGZnaVh0SnhkL2psYm9XLzQ5VTE4ZFdpcGZ6RlJmRzAyKzJjbi9sVHVmcTg0NTg3Y1VjK0U0Yi81dUxtNHZiMjFyL05abk54Y1gzbCsrMmRmdks3Ly9EQk1zQ1ArOVgxWmNtRVoyVFQ2SGZpMmF1cjhOYUg5OCs5TEl2UnVaNXdSLzU2Mml0bmFCeWtIeklhNjZvUDNsNGdRLzNkejNLUFFpL2IwT0tlMzNOcm4wTzJrM1BtZnpuR3BmTGZ2MUxUelhlVnVkWXVGOExITW84eW11ci8rYXBWWHkrQTFuNHZXcnU1Q0g5cGM1SVhiVS9oM0hmYmZlR045VTM1UjcvZWZhMzJ0SFR0THVkKzR2anFUODZ2dGZ1WnhpQ3ZnUmhsUDVhL0NEckZHaFg2VjM5ZHR2anhHOTFqV2RMLzhPL2JqZXVrNmJDTHEycFB4RUh2dUo5dHJuMi92SzQ3YnZvZ3YydjVYYXFmUW1Qcy95STZzYkJYZHRYMTByWFFmVnUwaWs5ZVhNOHcxbDJSNlhOckgzM1pLbHExbjFsWHRYWkRYUzVjYWFNam5kNC95Y2k3cjlPSmw0RTJhYU0vU2J0RWE2bC85dlR5TE0zNDc3NldCR1doTnJFZ0tBdDR1WDRQaE5jM3psUk1IK21ZMzVRWCthY1RIZVN3NzlFM0dQTTlLSWFKVG10RVMvRkp0K1kvMGh2WmNXZFdudm5SK1htT2YzanE3ejJOOE5mbjMrZTVWaitoTWZJOThqZUh6eFU0eVdTTXZPQmVvai81V2RmeFp5Rmg4MHJjdFR6WC9FT3hWN1...",
}
```

### Exemplo de uma resposta mal sucedida (código 401 - UNAUTHORIZED)
Se token enviado não for válido, o servidor devolve ```"401 - Token not valid"```. Isto significa que o token ***JWT*** enviado não é válido. Isto pode acontecer em várias situações, como por exemplo, se o token já não existir.