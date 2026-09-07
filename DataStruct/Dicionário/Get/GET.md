```python
# Lê a linha de entrada e separa os produtos em uma lista
produtos = input().strip().split()
print(produtos)
mais_frequente = None
maior_contagem = -1
producte = {}
# Percorra a lista original para garantir o critério de desempate (primeira ocorrência)
for produto in produtos:
    producte[produto] = producte.get(produto, 0) + 1
```

A ideia do GET é fazer uma contagem. Ele verifica a lista e caso o valor já exista no dicionário, ele soma no valor, caso não, adiciona ao dicionário. 

[[Dicionário]]