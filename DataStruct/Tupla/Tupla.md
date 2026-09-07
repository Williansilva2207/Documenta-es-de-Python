## Definição

> São ideais para representar listas de valores constantes e para realizar operações de empacotamento e desempacotamento de valores

## Declaração

> Usa-se parêntese (  ) ao invés de colchetes [  ]

```python
tupla = (1,)
#É fundamental a vírgula após o elemento para a declaração da tupla 
```

Podemos criar um vazia também:

```python
tupla = ()
```

Podemos usar a função <font color="#f79646">tuple( )</font> para criar uma tupla a partir de uma lista:
```python
l = [1,2,3]
T = tuple(l)
#Saída: (1, 2, 3)
```

Ela pode ser criada por concatenação:
```python
frutas = ("maçã", "banana")
legumes = ("cenoura", "batata")
comida = frutas + legumes
print(comida)
#Saída: ('maçã', 'banana', 'cenoura', 'batata')
```

## Ações

Podemos ter uma lista dentro de uma Tupla:
```python
tupla = ("a",["b","c"])
print(len(tupla))
#Saída: 2
```

Posso alterar a lista dentro da tupla:
```python
tupla[1].append("e")
#Saída: ('a',['b','c','e'])
```

[[DataStruct]]