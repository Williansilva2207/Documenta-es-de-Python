```python
from fastapi import FastAPI
from Hero import Hero

app = FastAPI()

@app.get("/")

async def read_user_item():
    item = {"hello": "world"}
    return item

@app.post("/batman")
async def post_name(hero: Hero):
    item = hero
    return {"Sucesso": "Envio bem sucedido"}
    
```

[[FastAPI]]

