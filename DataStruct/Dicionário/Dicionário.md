## Definição

> É composto de um conjunto de chaves e valores:
>  Ele consiste em relacionar uma chave a um valor específico

Criamos dicionários utilizando chaves:
```python
tablea = {} #Aqui já criei um dicionário

tabela = {"Alface":0.45,
		  "Batata":1.20,
		  "Tomate":2.30,
		  "Feijão":1.50}
```
<mark style="background:rgba(163, 67, 31, 0.2); font-size: 11px; font-style: italic">As chaves são como os índices do dicionário</mark>

## Pondo Valores
##### 1° CASO: Chave Existe

> O valor já associado à chave já existente é alterado pelo novo que foi atribuído à ela.

```python
print(tabela["Tomate"])
#2.30
tabela["Tomate"] = 4.50
print(tabela["Tomate"])
#4.50
```

##### 2° CASO: Chave Não Existe

> Um nova chave será criada/adicionada ao dicionário.

```python
tabela["Cebola"] = 3.60
print(tabela["Cebola"])
#3.60
```

## Verificação

> A ferramenta <font color="#92cddc">in</font> pode ser utilizada para verificar se uma específica chave existe no dicionário

```python
print("Manga" in tabela)
#False
```

## Funções
#### Keys()

```python 
print(tabela.keys())
#dict_keys(['Alface', 'Batata', 'Tomate', 'Feijão'])
```

#### del
```python
del tabela["Feijão"]
print(tabela.keys())
#dict_keys(['Alface', 'Batata', 'Tomate'])
```

#### values()
```python
print(tabela.values())
#dict_values([0.45, 1.2, 2.3])
```



[[DataStruct]]