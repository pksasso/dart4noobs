# 03 - Variáveis e Constantes

Em programação quando você quer guardar informações para seu programa usar você precisará de variáveis e constantes. Elas são em poucas palavras um espaço onde você pode guardar coisas como um nome, um número ou uma lista, para poder usar depois.

# Variáveis

No dart quando se quer guardar um dado que pode ser alterado ao decorrer da aplicação usamos variáveis, para definir uma variável basta colocar `var` e o nome que você quer dar a ela

```dart
var nome;
```

Caso não inicialize uma variável como algum valor ela por padrão é iniciada como `null`.

Por padrão quando não é explicitado se algo é `var` ou `const` ela será uma variável.

# Constantes

Caso haja algum valor que não vá mudar no programa se usa uma constante, é usado `const` para isso. As constantes DEVEM ser inicializadas com algum valor, do contrário o programa dará um erro de compilação.

```dart
const pi = 3.14;
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
