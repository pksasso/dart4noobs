# 02 - Tipos

Dart é uma linguagem chamada type-safe, ou seja, você deve informar qual tipo de dados você armazenará em uma posição de memória (variável, constante, parâmetro de função ou tipo de retorno de função) e uma vez definido este tipo, a linguagem garante que somente operações permitidas podem ser executadas neles. Complicado? Vamos a um exemplo: dada uma variável do tipo bool (true ou false) não será possivel somar 10 a essa variável.

```dart
bool valorLogico = true;
double valorDecimal = 10.0;
print(valorLogico + valorDecinmal)
```
Resposta do dart:

Error: The operator '+' isn't defined for the class 'bool'
Try correcting the operator to an existing operator, or defining a '+' operator.
  print(valorLogico + valorDecimal);
                    ^

Essa mensagem de erro nos diz algumas coisas mas a mais importante, no momento, é que não existe uma operação de adição para o tipo bool. Não faz sentido somar bool com double. 

Outra informação importante: "class 'bool'" nos diz que bool é uma classe. Assim como double, int, String. Não temos, em dart, tipos primitivos como em outras linguagens tais como C, Java, C#. Todos os tipos são objetos. 

Veja isso:

```dart
int valorInteiro = 10.0.toInt();
print(valorInteiro);
```

Estamos acessando o método toInt() do objeto do tipo double representado pelo valor 10.0, convertendo esse valor para um inteiro e este valor será armazenado na variável valorInteiro. Oportunamente falaremos mais sobre classes e objetos. Por ora, podemos considerar os tipos simplesmente como os tipos de dados que conhecemos.

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

E o tipo char? O que se usa para um único caracter? Um caracter é tratado como uma String normal.

<p align="center">
  <a href="01-Sintaxe.md">
    <img src="../../4noobsAssets/anterior.svg" height=35>
  </a>
  <a href="03-VariaveisEConstantes.md">
    <img src="../../4noobsAssets/proximo.svg" height=35>
  </a>
</p>