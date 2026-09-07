A ideia do post é criar um novo objeto.

Primeiramente, precisamos entender que a requisição do http header, especifica a codificação do body, ao mesmo tempo, deixa claro o tipo de aplicação que está sendo enviada: JSON ou XML. Normalmente se trabalha com JSON, o que vai o meu caso até agora.

Ora, mas o que usaremos para que o python compreenda o JSON?
- Isso é simples. Para isso existe o [[Pydantic]] (*Leia a documentação*)

```python
from fastapi import FastAPI
from pydantic import BaseModel

app = FastAPI()


class Item(BaseModel): #O recomendável é por essa parte em uma pasta /schema
    name: str
    price: float
    is_offer: bool | None = None


@app.get("/")
def read_root():
    return {"Hello": "World"}


@app.get("/items/{item_id}")
def read_item(item_id: int, q: str | None = None):
    return {"item_id": item_id, "q": q}


@app.put("/items/{item_id}")
def update_item(item_id: int, item: Item):
    return {"item_name": item.name, "item_id": item_id}
```


[[Métodos]]

