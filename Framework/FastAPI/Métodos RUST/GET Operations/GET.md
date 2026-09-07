Devemos ter em mente a estrutura de uma requisição via http:

> https://www.google.com:80/search?q=FastAPI

Aqui iremos dissecar as principais partes da requisição GET, que são:
- Host, e.g. → www.google.com
- Port, e.g. → **80 (Padrão)**
- Path, e.g. → **/search**
- Query Sting, e.g. → **?q=FastAPI**

Praticamente, com o FastAPI, iremos simplificar essa requisição.

```python
@app.get("/hello") #Aqui temos o path
def get_hello(name:str = "Alan"): #A lista de parâmetros sendo passada
	return {"message": f"hello{name}"} #E o que a requisição irá passar
```

Exemplo da documentação oficial do FastAPI:
```python
from fastapi import FastAPI

app = FastAPI()


@app.get("/")
def read_root():
    return {"Hello": "World"}


@app.get("/items/{item_id}")
def read_item(item_id: int, q: str | None = None):
    return {"item_id": item_id, "q": q}
```


[[Métodos]]