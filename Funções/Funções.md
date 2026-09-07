## As 2 Regras
* Deve resolver apenas um problema
* Quanto mais genérica for sua solução, melhor ela será em longo prazo.

>! Se as funções só servem ao programa, <u>considere um sinal de alerta.</u>

```python
def soma(l):
	total = 0
	x = 0
	while x<5:
		total += l[x]
		x += 1

	return total

#Se prestar atenção essa função só vai percorrer em listas com 5 itens.
#ou seja apenas no contexto do programa que tem uma lista de 5 itens
```

## Globais e Locais

> <u>Variáveis Locais</u>: Acessadas apenas nas funções;
> <u>Variáveis Globais</u>: Declaradas fora da função e podem ser acessadas por outras.

## Recursividade

Fibonacci Exemple:
```python
def fibonacci(n):
	if n<=1:
		return n
	else:
		return fibonacci(n-1) + fibonocci(n-2)
```

## Validação

* Verificação dos dados que estão entrando no programa;
* É muito importante para evitar erros difíceis de detectar depois de ter escrito o programa.

> Sempre verifique se os dados estão na faixa e no formato adequado.


## Empacotamento e Desempacotamento de Parâmetros

> Digamos que tenhamos uma lista **L** com dois elementos

```python
L = [1,2]
```

> Quero pegar o L[0] e L[1], sem ter que fazer o seguinte comando:

```python
soma(L[0],L[1])
```

> Podemos fazer:

```python
soma(*L)
```

[[Python]]