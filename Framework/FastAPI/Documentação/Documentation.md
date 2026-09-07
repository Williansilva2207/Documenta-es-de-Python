
# First Step

Bem, em primeiro lugar importamos o FastAPI
```python
from fastapi import FastAPI
```

Logo após isso, há a instanciação

```python
app = FastAPI()
```

> Esta é a parte mais importante da aplicação para criar toda a API

Feito isso, posso criar o meu path, ou caminho.

```
/items/foo
```

> É muito comum chamar o path de "endpoints" ou "routes"

Temos algumas operações ou, "Métodos HTTP" que conhecemos as principais delas:
- POST
- GET
- PUT
- DELETE

Também há outras que a documentação chama de mais exóticas, como:
- OPTIONS
- HEAD
- PATCH
- TRACE

Enfim, vamos definir o que a documentação chama de *path operation decorator*

```python
@app.get("/")
```

Depois desse, fica claro que precisamos criar os decorator antes das funções que iremos desenvolver. E nitidamente, cada operação que vimos é declarada da mesma forma:

- @app.post
- @app.put
- @app.delete
-  [...]

Feito isso, podemos criar nosso *path operation function*

```python
async def root():
	return{"message": "Hello world!"}
```



# Path Parameters

Neste ponto, definimos nas funções que criamos, que chave, e o tipo de valor que ela deve retornar, a nossa API espera naquela função.

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/items/{item_id}")
async def read_item(item_id):
	return {"item_id": item_id}
```

→ Caso queira, faça um teste pondo na função read_item( ), um parâmetro com um nome diferente do que se espera no *path*, isso acarretará em um erro.

Dito isso, teste o seguinte caminho:

>http://127.0.0.1:8000/items/foo

→ Ele receberá o foo e retornará como mensagem o foo.

#### Path Parameters With Types

Diante de tudo isso, podemos passar nos parâmetros, o tipo de dado que esperamos receber:

```python
@app.get("/items/{items_id}")
def get_test(items_id: int):
    return {"message": items_id}
```

→ Note que aqui esperamos um <font color="#f79646">int</font>, ou seja, queremos um dado do tipo inteiro sendo passado para a gente.

> Todas essa para de validação de Parâmetros, vamos precisar do nosso querido [[Pydantic]] que irá realizar essas serializações de dados. 

Caso eu queira padronizar um tipo de retorno, onde o caminho passa algo predefinido, usa-se muito o Enum.

```python
from enum import Enum

class ModelName(str, Enum):
    alexnet = "alexNet"
    resnet = "resNet"
    lenet = "leNet"
```

→ Aqui declaramos o Enum, digamos que a pessoa tá declarando um modelo específico e ele vai retornar o tipo de modelo que ela busca.

```python
from fastapi import FastAPI
from modelName.ModelName import ModelName

app = FastAPI()

@app.get("/models/{models_name}")
async def read_model(model: ModelName):
    models = [ModelName.alexnet, ModelName.lenet, ModelName.resnet]
    for model_s in models:
        if model is model_s:
            return {"model": model_s}
```

→ Bem, diante disso tudo, temos outra situação bastante interessante. Que é quando precisamos acessar um outro caminho dentro do caminho:

1. /files/{file_path};
2. Dentro de file_path, tem algo como /home/johndoe/myfile.txt
3. Ou seja, o caminho todo fica: /files/home/johndoe/myfile.txt

→ Qual é o problema ? A OpenAPI não possui um suporte para isso, no entanto, o FastAPI tem, utilizando uma ferramenta interna do Starlette

```python
from fastapi import FastAPI
from modelName.ModelName import ModelName

app = FastAPI()

@app.get("/files/{file_path:path}")
async def read_file(file_path: str):
    return{"file_path": file_path}
```

>{file_path : path} → estou praticamente dizendo, eu espero que a string file_path tenha um caminho válido.



[[FastAPI]]