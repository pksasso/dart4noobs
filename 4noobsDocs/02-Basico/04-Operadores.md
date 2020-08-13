# 04 - Operadores

## Operadores Aritméticos

Os operadores aritméticos são os símbolos para fazer as contas de matemática que você aprendeu no colégio.

Os mais simples são :

- Soma ( `+` )
- Subtração ( `-` )
- Multiplicação ( `*` )
- Divisão ( `/` )

Existem também alguns mais complexos como :

- Divisão retornando um número inteiro ( `~/` ), o resultado sempre será arredondado para baixo
- Resto da divisão ( `%` ), ao invés de retornar o resultado da divisão da quanto teve de resto na conta

Exemplos:

```dart
// Os operadores basicos

print( 1 + 2 ); // 3
print( 2 - 1 ); // 1
print( 2 * 3 ); // 6
print( 4 / 2 ); // 2
print( 5 / 2 ); // 2.5

//Os mais complexos

print( 3 ~/ 2 ); // 1, o resultado da divisao normal seria 1.5 , mas como esse operador
//arredonda para baixo ele pega só o número antes da virgula.
print( 5 % 2); // 1, esse retorna o resto da divisão, 5 dividido por 2 da 2 e sobra 1,
//essa sobra que ele retorna
```

## Incremento e decremento

Para facilitar algumas contas básicas existem os incrementos e decremento, que adicionam 1 ou diminuem 1

- `var++` - soma um na sua variável
- `++var` - também soma um mas tem uma diferença que será tratada abaixo
- `var--` - Diminuir 1 na sua variável
- `--var` - Diminui de uma forma diferente a ser explicada

exemplos:

```dart
// O var++ altera a variavel que voce disse parra + 1
int a = 1;
a++;
print( a ); // 2

// e o var-- para -1

int a = 2;
a--;
print( a ); // 1
```

Quando vai colocar o valor de uma variável dentro de outra a ordem do `++` e do `--` muda quando essa soma irá acontecer

exemplo:

```dart
var a, b; // criando duas variaveis na mesma linha

a = 0; // inicializando a para ter o valor 0
b = a++; // soma 1 na variavel a DEPOIS de colocar o valor de a em b,
// ou seja primeiro b recebe o valor de a, que é 0, depois o a soma em + 1 e vira 1.
print( a ); // 1
print( b ); // 0

a = 0; // define a como 0
b = ++a; // Soma 1 no a ANTES de colocar o valor dele no b, ou seja, a vira 1 e só então
// o b recebe o valor de a
print( a ); // 1
print( b ); // 1

//a mesma lógica se repete para o --
```

## Operadores de igualdade relacionais

Esses também são velhos conhecidos da escola.

- Igualdade ( `==` ) , retorna `true` se os dois lados fores iguais ou `false` for diferente
- Desigualdade ( `!=` ), retorna `true` se os lados fores diferentes e `false` se forem iguais
- Maior que ( `>` ) retorna `true` se o lado esquerdo for maior que o direito
- Menor que ( `<` ) retorna `true` se o lado direito for maior que o esquerdo
- Maior ou igual ( `>=` ) retorna `true`se o lado esquerdo for maior ou igual ao direito
- Menor ou igual ( `<=` ) retorna `true` se o lado esquerdo for menor ou igual ao direito

### Operadores lógicos

Essa parte pode parecer meio estranha se você nunca ouviu falar sobre lógica booleana, pode ser bom pesquisar um pouco caso queira entender um pouco mais sobre.

- OU ( `||` ), retorna `true` se algum dos lados for verdade
- E ( `&&` ), para essa expressão retornar `true` é necessário que os dois lados dela seja verdadeiros

exemplos:

```dart
int a = 1;
int b = 2;

print( a == b || a == a ); // true,  pois a e b não são igual mas a é igual a a
print( a == b && a == a ); // false, pois o E, os dois lados precisam ser verdade,
//como a primeira parte já é falsa ela ja retorna false
```
