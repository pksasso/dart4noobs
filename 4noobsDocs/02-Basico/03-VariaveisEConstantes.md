# 03 - Variáveis e Constantes

Em programação quando você quer guardar informações para seu programa usar você precisará de variáveis e constantes. Elas são em poucas palavras um espaço onde você pode guardar coisas como um nome, um número ou uma lista, para poder usar depois.

# Variáveis

No dart quando se quer guardar um dado que pode ser alterado ao decorrer da aplicação usamos variáveis, para definir uma variável basta colocar `var` e o nome que você quer dar a ela

```dart
var nome;
```

Caso não inicialize uma variável como algum valor ela por padrão é iniciada como `null`.

Por padrão quando não é explicitado se algo é `var` ou `const` ela será uma variável.

A partir da versão do Dart `2.12` foi introduzido o `null safety` e por padrão todos os tipos não podem ser anuláveis.

```dart
var i = 42; // Inferêcia para o tipo int.
String name = getFileName();
final b = Foo(); 
```

Para indicar que uma variável pode ter seu valor nulo, basta adicionar um tipo que permita nulo. O nome deste tipo é o mesmo do que quer utilizar seguido de `?`.

```dart
int? aNullableInt = null;

```

Mas não se engane: '?' não é um operador acrescentado ao tipo e sim um outro tipo, conforme se vê na documentação do dart: [Using nullable types](https://dart.dev/null-safety/understanding-null-safety#using-nullable-types)


# Constantes

Caso haja algum valor que não vá mudar no programa se usa uma constante, é usado `const` para isso. As constantes DEVEM ser inicializadas com algum valor, do contrário o programa dará um erro de compilação.

```dart
const pi = 3.14;
```

Do mesmo modo que as variáveis, as constantes também podem ser declaradas com `final` ao invés de `const`. A diferença entre `const` e `final` é que `const` é uma constante em tempo de compilação, ou seja, o valor da constante é conhecido em tempo de compilação. Já `final` é uma constante em tempo de execução, ou seja, o valor da constante é conhecido em tempo de execução.

```dart
main() {
  const res = multiplicar(2, 2); // gera erro, o resultado da multiplicação não é conhecido antes de executar o programa
  final x = multiplicar(2, 2); // x = 4
  x = 10; // gera erro, uma variável 'final' não pode ter seu valor alterado depois de inicializada
}

// função que retorna o resultado da multiplicação de dois números, apenas para exemplificar
// mais informações sobre funções no capítulo 7 - Funções
int multiplicar(int valor1, int valor2) {
  return valor1 * valor2;
}
```

# Inferência de tipos

No dart caso você use `var` ou `const` sem dizer o tipo que será guardado ele ira definir o tipo de acordo com o tipo do valor que for inicializado.

```dart
var a = 1;
print(a is int); // true

const b = 'he4rt';
print(b is String); // true
print(b is double); // false
```

Porém uma vez que a variável é inicializada o tipo dela não pode mudar, ou seja, se você criar `var a = 1;` e depois disso tentar fazer `a = 'texto';` isso não será permitido, pois `a` foi definida como um `int`.

Apesar de existir a inferência de tipos pode ser bom definir explicitamente qual o tipo da variável, isso ajuda na leitura do código.

```dart
int a = 1;
const String b = 'he4art';
```

<p align="center">
  <a href="02-TiposPrimitivos.md">
    <img src="../../4noobsAssets/anterior.svg" height=35>
  </a>
  <a href="04-Operadores.md">
    <img src="../../4noobsAssets/proximo.svg" height=35>
  </a>
</p>
