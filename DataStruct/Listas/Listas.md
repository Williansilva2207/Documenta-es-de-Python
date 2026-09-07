## Cópia e Fatiamento de Listas

> Digamos que eu tenha duas listas, L e M:

```python
l = [1,2,3]
m = []
```

Para que <font color="#92cddc">m</font> consiga copiar o <font color="#92cddc">l</font> eu não posso só simplesmente fazer a atribuição: 
```python
m = l
```

A forma correta de realizar isso é:
```python
m = l[:]
```

> **Mas por que ?**
> É necessário lembrar que o python trabalha por referência. Logo, m = l, estou passando um ponteiro para o mesmo local de l. 

### Fatiamento

```python
l = [1,2,3,4,5]
print(l[0:5])
#Aqui faço uma especificação do intervalo que eu quero da lista. Do índice 0 até o 4.
#Print: 1,2,3,4,5
```

```python
print(l[:5]) #estou pedindo para printar os 5 primeiros elementos
```

```python
print(l[:-1]) #Todos, menos o último
print(l[:-2]) #Todos, menos os dois últimos
```

```python
print(l[3:]) #Mostrar do elemento índice 3 até o do último índice
```

```python
print(l[:3]) #Do índice 0 até o do índice 2
```




## Append e Extend (Curiosidade)

>**Append**: Adiciona uma lista a outra;
>**Extend**: Adiciona cada elemento da lista na outra.

```python
lista_test = ["d","e"]
l.append([lista_test])
print(l)
#Irá mostrar: [1,2,3,["d","e"]]
```

```python
l.extend(lista_test)
print(l)
#Irá mostrar: [1,2,3,"d","e"]
```

## For: Enumerate

```python
l = [5,9,13]
for x, e in enumerate(l):
	print(f"[{x}]{e}")
#Vai mostrar:
#[0]5 
#[1]9 
#[2]13
```

 → <font color="#92cddc">x</font> vai retornar a posição. Sempre o primeiro item do for + enumerate(lista) vai retornar o índice.
 









[[DataStruct]]
