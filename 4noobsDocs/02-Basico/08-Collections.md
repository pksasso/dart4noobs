# 08 - Collections

Grande parte do tempo de desenvolvimento é utilizado para processar coleções de informações. Ou seja, processar dados. Não à toa, os primeiros cursos da área de tecnologia orientados a desenvolvimento eram chamados de...[*Processamento de Dados*](https://pt.wikipedia.org/wiki/Processamento_de_dados)

Em dart existem recursos para processarmos esses dados além de variáveis. São tratados em conjunto nas *Collections*, que são nada mais que conjuntos de dados, ou melhor, coleções de dados.

## Lists (List)

Como o nome já diz esse tipo são listas.

Muitas vezes criar varias variáveis se torna um negócio meio desnecessário, para isso existem as listas, a sintaxe delas é a seguinte:

```dart
var lista1 = [ 1, 2, 3 ];
var lista2 = [ 'a', 'b', 'c' ];
var lista3 = [ 1, 2.5, 3 ];
```

Basta colocar todos seus valores dentro de colchetes e separados entre virgulas. São os equivalentes aos vetores (arrays de outras linguagens).

É importante saber que não é possível misturar tipos de diferentes dentro de uma lista, aqui eu não especifiquei se a lista é de inteiros ou texto, mas o dart foi capaz de descobrir de acordo com o conteúdo das listas.

Se você é uma pessoa atenta pode estar se perguntando, "Poxa, mas lá no inicio você disse que números inteiros e números com virgulas tem tipos diferentes, e na lista3 tem números inteiros e com virgula juntos, por que não da erro ?". Muito bem notado, existe uma forma de verificar o tipo de um valor , é a palavra `is` ela compara o tipo da esqueda com o que você esta perguntando se é e retorna verdadeiro( true ) ou falso( false ), vamos ver o que retorna.

Para acessar os itens de uma lista usamos o nome da lista e a posição do ítem, as listas são *zero based*, ou seja, a primeira posição é 0, a segunda 1 e assim por diante.

```dart
var lista3 = [ 1, 2.5, 3 ];
print(lista[0] is double); // true
print(lista[1] is double); //true
print(lista[2] is double); //true
```

Percebeu o que aconteceu? O dart converteu todos os números para double ! E isso faz todo sentido, já que 1 pode ser escrito com virgula na forma 1.0, mas isso só acontece com números, se você tentar colocar um texto junto isso não vai dar certo.

Se por acaso você quiser explicitar o tipo da sua lista pode fazer da seguinte forma:

```dart
List<int> lista1 = [ 1, 2, 3 ];
List<String> lista2 = [ 'a', 'b', 'c' ];
List<double> lista3 = [ 1, 2.5, 3 ];
```

Peraí. Perdi a inferência de tipos do dart. Calma lá, podemos fazer diferente:

```dart
var lista1 = <int>[ 1, 2, 3 ];
var lista2 = <String>[ 'a', 'b', 'c' ];
var lista3 = <double>[ 1, 2.5, 3 ];
```

Pronto!

Podemos realizar operações com as listas. Como, por exemplo, localizar a posição de um valor:

```dart
var lista2 = <String>[ 'a', 'b', 'c' ];
final posicao = lista2.indexOf('b'); // retornará 1

print(lista2[posicao]);
/*
b
*/
```

Podemos adicionar elementos à lista:

```dart
var lista2 = <String>[ 'a', 'b', 'c' ];
lista2.add('x');
lista2.add('y');

print(lista2);
/*
[a, b, c, x, y]
*/
```

Podemos remover elementos da lista:

```dart
var lista2 = <String>[ 'a', 'b', 'c' ];
lista2.remove('a');
print(lista2);
/*
[b, c]
*/
```

Listas também possuem propriedades:

```dart
var lista2 = <String>[ 'a', 'b', 'c' ];
lista2.first; // a
lista2.last; // c

lista2.isEmpty // false
lista2.isNotEmpty // true

lista2.length // 3
lista2.length > 0 // true
```

Podemos juntar lista com o *spread operator* (...)

```dart
const americaDoSul = [ 'Argentina', 'Brasil', 'Chile' ];
const americaDoNorte = ['Canada', 'Estados Unidos', 'México'];
const america = [...americaDoSul, ...americaDoNorte];
print(america);
/*
[Argentina, Brasil, Chile, Canada, Estados Unidos, México]
*/
```

Podemos, ainda, utilizar o collection if para condicionar a montagem de uma lista:

```dart
  const americaDoSul = [ 'Argentina', 'Brasil', 'Chile' ];
  const americaDoNorte = ['Canada', 'Estados Unidos', 'México'];
  const americaCentral = ['Costa Rica', 'Guatemala', 'Panamá'];

  const bool incluirAmericaCentral = true;

  const america = [...americaDoSul, ...americaDoNorte, if(incluirAmericaCentral) ...americaCentral];

  print(america);
  /*
  [Argentina, Brasil, Chile, Canada, Estados Unidos, México, Costa Rica, Guatemala, Panamá]
  */
```

## Sets (Set)

Funciona de forma muito similar as listas, porém ele não pode ter valores iguais e a notação ao invés de colchetes usa chaves:

```dart
var conjuntoInteiros = { 1, 2, 3 };
var conjuntoVogais = { 'a', 'e', 'i', 'o', 'u' };
```

Além disso, temos as operações específicas de conjuntos:

### Contains

Método contains retorna verdadeiro (true) se existir o elemento informado. false caso não exista.

```dart
var conjuntoInteiros = {0, 1, 2, 3 };
print(conjuntoInteiros.contains(3)); // true
```

### Intersections

Dados dois conjuntos, o método *intersection* retorna um novo conjunto com a intersecção entre estes. Os elementos encontrado em ambos.

```dart
var conjuntoInteiros = {0, 1, 2, 3 };
var conjuntoOutrosInteiros = {-2, -1, 0, 2,};

print(conjuntoInteiros.intersection(conjuntoOutrosInteiros)); 
/*
{0, 2}
*/
```

### Unions

Já o método *union* retornará um novo conjunto com valores únicos combinando dois conjuntos:


```dart
var conjuntoInteiros = {0, 1, 2, 3 };
var conjuntoOutrosInteiros = {-2, -1, 0, 2,};

print(conjuntoInteiros.union(conjuntoOutrosInteiros)); 
/*
{0, 1, 2, 3, -2, -1}
*/
```

## Maps (Map)

Funciona bem parecido com listas e sets, porém seu diferencial é que ele utiliza pares de chave e valor:

```dart
var pessoa = {
	//chave:  valor
	'nome': 'João',
	'idade': '20',
	'email': 'joao@email.com'
}
```

Percebeu ? No map nós conseguimos dar 'nomes' para as nossa posições, e de forma similar as listas podemos acessar seus dados, porém ao invés de usarmos a posição que queremos podemos usar a chave dela

```dart
var pessoa = {
	//chave:  valor
	'nome': 'João',
	'idade': '20',
	'email': 'joao@email.com'
};

print(pessoa['idade']); // 20
print(pessoa['nome']); // João
```

Assim como o `Set`, também há uma forma diferente de mexer com eles que veremos no futuro.

