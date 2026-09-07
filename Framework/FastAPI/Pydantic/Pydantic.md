> Responsável em serializar e desserializar  o arquivo JSON. Explicando de maneira esdrúxula, ele converte o JSON para dicionário pro python e retorna o dicionário em JSON.

Exemplo:
```python
from pydantic import BaseModel

class Review(BaseModel):
	num_stars: int
	text: str
	public: bool = False

class MovieReview(BaseModel):
	movie: str
	review: Review
	
```

[[FastAPI]]