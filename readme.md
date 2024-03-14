# Documentação oficial do backoffice do algorithmi
## Para instalar as dependências:
1. Instalar [Python](https://www.python.org/downloads/), caso ainda não esteja instalado
2. Instalar [VSCode](https://code.visualstudio.com/download), caso ainda não esteja instalado
3. Clonar o repositório
4. Dentro da pasta raíz, executar no terminal:
- ```python -m venv venv```, para criar o ambiente virtual
- ```python -m pip install mkdocs --user```, para instalar o MKDocs
- ```python -m pip install mkdocs-material --user```, para instalar o tema que é utilizado na documentação
6. Escrever no terminal ```python -m mkdocs serve``` para iniciar o servidor
7. Aceder no browser a <http://localhost:8000/>
8. Após terminar a edição da documentação, executar o comando ```python -m mkdocs gh-deploy``` dentro da pasta raíz, para automaticamente publicar a documentação na web
9. Finalmente, fazer push das alterações para o branch **"main"**.
  
