## Definição e Declaração
São uma estrutura de dados que implementam operações de **união**, **interseção**, **diferença**, etc.
```python
a = set() #declaração
a.add(1)
a.add(2)
a.add(3)
print(a)
#Saída: {1,2,3}
```

> E se eu tentar .add(1) novamente ?

```python
a.add(1)
print(a)
#Saída: {1,2,3} 
#Ele não vai adicionar o mesmo número
```


## Funções

#### União

> Realizada pelo operador **|** , resultando em um novo conjunto com todos os elementos

```python
a = {0,1,2,3,-1}
c = set([4,5,6])
print( a | c)
#Saída: {0,1,2,3,4,5,6,-1}
```

#### Interseção

> Operação que retorna apenas os elementos em comum entre os dois conjuntos.

* Pode ser feito com: & ou . intersection()
```python
c.add(3)
print(a & c) #Intersecção dos conjuntos
print(a.intersection(c))
#{3} 
#{3}
```

#### Diferença

> O resultado mostra os elementos que não estão em **a** e **c**

```python
print(a-c)
print(a.difference(c))
#{0, 1, 2, -1} 
#{0, 1, 2, -1}
```

#### Diferença Simétrica

> Elementos que não são comuns nos dois.

```python
print(a^c)
print(a.symmetric_difference(c))
#{1,3,4,5}
#{1,3,4,5}
```



[[DataStruct]]