# 02 - Tipos primitivos

Para usar alguma valor no dart é necessário dizer o tipo de dado que aquela variável irá guardar;

No dart as variaveis tem tipos , os mais basicos são int , double, bool, String, Lists, Sets e Maps.

Os três últimos são mais complicadinhos e serão explicados no final.

## Integer ( int )

São números inteiros como 1 2 3.

```dart
int num = 12;
```

## Double ( double )

São números com ponto flutuante, basicamente números com virgula.

```dart
double pi = 3.14;
double gravidade = 9.8;
```

## Boolean ( bool )

São os tipos booleanos, o que é basicamente ser falso (false) ou verdadeiro (true).

```dart
bool verdadeiro = true;
bool falso = false;
```

## String ( String )

São sequencias de caracteres, um texto ou frase. Deve ser declarada entre aspas duplas `" "` ou simples `' '` .

```dart
String frase = 'He4art devs é a mais braba';
```

Podemos juntar uma string com outra, basta usar o `+`

```dart
String frase = 'He4art devs é';
String frase2 = ' a mais braba';
print(frase + frase2); // He4art devs é a mais braba
```

Podemos juntar uma string com os outros tipos usando `$nomeDaVariavel` dentro da String, e caso seja mais de uma variável use `${num1+num2}`

```dart
int num1 = 5;
String frase = 'He4art devs é';
String frase2 = ' ${num1*2} vezes a mais braba';
print(frase + frase2); // He4art devs é a mais braba
```

## Lists (List)

Como o nome já diz esse tipo são listas.

Muitas vezes criar varias variáveis se torna um negócio meio desnecessário, para isso existem as listas, a sintaxe delas é a seguinte

```dart
var lista1 = [ 1, 2, 3 ];
var lista2 = [ 'a', 'b', 'c' ];
var lista3 = [ 1, 2.5, 3 ];
```

Basta colocar todos seus valores dentro de colchetes e separados entre virgulas.

É importante saber que não é possível misturar tipos de diferentes dentro de uma lista, aqui eu não especifiquei se a lista é de inteiros ou texto, mas o dart foi capaz de descobrir de acordo com o conteúdo das listas.

Se você é uma pessoa atenta pode estar se perguntando, "Poxa, mas lá no inicio você disse que números inteiros e números com virgulas tem tipos diferentes, e na lista3 tem números inteiros e com virgula juntos, por que não da erro ?". Muito bem notado, existe uma forma de verificar o tipo de um valor , é a palavra `is` ela compara o tipo da esqueda com o que você esta perguntando se é e retorna verdadeiro( true ) ou falso( false ), vamos ver o que retorna.

Para pegar os itens de uma lista usamos o nome da lista e a posição que queremos ver, vale lembrar que em programação sempre começa a contar do 0.

```dart
var lista3 = [ 1, 2.5, 3 ];
print(lista[1] is double); // true
print(lista[0] is double); //true
print(lista[2] is double); //true
```

Percebeu o que aconteceu ? O dart converteu todos os números para double ! E isso faz todo sentido, já que 1 pode ser escrito com virgula na forma 1.0, mas isso só acontece com números, se você tentar colocar um texto junto isso não vai dar certo.

Se por acaso você quiser explicitar o tipo da sua lista pode fazer da seguinte forma:

```dart
List<int> lista1 = [ 1, 2, 3 ];
List<String> lista2 = [ 'a', 'b', 'c' ];
List<double> lista3 = [ 1, 2.5, 3 ];
```

## Sets (Set)

Funciona de forma muito similar as listas, porém ele não pode ter valores iguais e a notação ao invés de colchetes usa chaves

```dart
var set1 = { 1, 2, 3 };
var set2 = { 'a', 'b', 'c' };
```

Esse tipo é um pouco mais complexo, veremos como mexer com ele mais a frente.

## Maps (Map)

Funciona bem parecido com listas e sets, porém seu diferencial é que ele utiliza chave e valor, já vou mostrar o que é isso

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
