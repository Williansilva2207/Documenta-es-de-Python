 [[Python]] #POO 
## Objeto

```python
objeto = NomeClasse()
```

## Classe
```python

class Televisao():
    def __init__(self, canal_begin = 0, canal_min = 2, canal_max = 14, conta = ""):
        super().__init__()
        self._conta = conta
        self.ligada = False
        self._canal = canal_begin
        self.canal_min = canal_min
        self.canal_max = canal_max
```

## Construtor
```python
class Televisao:
    def __init__(self, marca):
        self.marca = marca
        print(f"Uma TV da {self.marca} foi fabricada!")

# Aqui o __init__ é chamado automaticamente
minha_tv = Televisao("Samsung")
```

## Encapsulamento
#### Getter e Setter do Python
##### @property
- Transforma métodos em atributos;
- Ele serve como o .getter( ) do Java.

```python
@property
def canal(self):
	return self._canal
```

##### @.setter
- Similar o setter
```python
@canal.setter #fundamental o setter ter o mesmo nome da função property
def canal(self, canal):
	if(canal < self.canal_min):
       raise ValueError(f"Canal inválido! Escolha entre {self.canal_min} e {self.canal_max}.")
    self._canal = canal

```

#### Público e Privado

> Não há palavras reservadas, mas, convenções.
> → Usa-se **__** (underline)

```python
class Televisao(Tecnologia):

    def __init__(self, conta = ""):
        super().__init__()
        self._conta = conta
```

> Dito isso, não quer dizer que o atributo está realmente privado e impossível acessar ele, pois ainda é. O underline só nos permite saber que aquele atributo não pode ser acessado diretamente. 

## Herança

#### Herança Simples
```python
class Dispositivo:
    def __init__(self, marca: str):
        self.marca = marca
        self.ligado = False

    def ligar(self):
        self.ligado = True
        print(f"{self.marca} está agora LIGADO.")


class SmartTV(Dispositivo):
    def __init__(self, marca: str, sistema_operacional: str):
        super().__init__(marca)
        self.sistema_operacional = sistema_operacional

    def abrir_netflix(self):
        if self.ligado:
            print(f"Abrindo Netflix no {self.sistema_operacional}...")
        else:
            print("Erro: A TV está desligada!")

# --- Uso do código ---
minha_tv = SmartTV("Samsung", "Tizen")

minha_tv.ligar()          
minha_tv.abrir_netflix()  
print(f"Marca: {minha_tv.marca}") 
```

#### Herança Múltipla

```python
class A:
	pass

class B:
	pass

class C(A,B):
	pass
```

#### Polimorfismo
###### O Que São Interfaces ?

> Definem o que uma classe deve fazer e não o como.
> Define-se um contrato, onde são declarados os métodos e suas respectivas assinaturas

→ Python não tem a palavra reservada interface

###### Criando Com o ABC
```python
from abc import ABC, abstractmethod

class ControleRemoto(ABC):
	@abstractmethod
    def ligar(self):
        pass
        
class ControleDeTv(ControleRemoto):
    def ligar(self):
        print("ligando a
         Tv")
```
