# 07 - Funções

Uma função é uma parte do código que você pode querer separar para questões de organização e para diminuir repetições.

No dart é NECESSÁRIO que exista uma função chamada `main` todo o seu código deve rodar dentro dela, vamos ver agora como ela é.

```dart
void main () {
	
}
```

Temos aqui uma palavra nova, `void` , no inicio de toda função é necessário especificar o que ela irá retornar, no caso da `main`, não queremos que ela retorna nada , por isso usamos `void`. Mas é possível usar todos aqueles tipos de variáveis que já vimos ( `int`, `String` , `bool`, `double` entre outras ) como os retornos das funções, nesse caso lá no final da nossa função devemos usar um `return` seguido da variável que queremos retornar.

```dart
//antes do nome da função temos um int, definindo que ela irá retornar um numero inteiro
int multiplicaPorDois(int a){
	return a*2; // aqui fazemos o retorno da nossa função
}
```

Se você prestou atenção nossa função tem algo dentro dos `( )`, isso é chamado de parâmetros da função, ou então de assinatura da função.

## Parâmetros

Os parâmetros de uma função é algum dado que queremos passar para ela, de modo que ela pode usar esse dado para fazer alguma ação e nos retornar algo depois, no exemplo dado acima nossa função recebia como parâmetro um `int` que foi chamado de `a` e no corpo da função usamos esse a para multiplicar por 2 e retornar o valor novo.

Passando os parâmetros da forma acima eles são por padrão obrigatórios de forma que o nosso programa dará um erro caso ele não seja passado, vamos ver como passamos um parâmetro pra uma função

```dart
void main(){//definição da função main
	int a = 2;
	int b = 3;

	//chamada da função passando dois parametros e colocando seu retorno em uma variavel
	int c = multiplicaNumeros(a,b);
	
	print(c);
}

// definição da função multiplicaNumeros com 2 parametros
int multiplicaNumeros(int num1, int num2){ 
return num1 * num2;// retorno multiplicando seus parametros
}
```

Dessa vez passamos 2 parâmetros para a nossa função, note que eles devem ser separados por virgula.

Dentro da nossa função nossas variáveis `num1` e `num2` recebem os valores dependendo da ordem que eles são passados na chamada, no nosso exemplo passamos `a` e `b` nessa ordem, logo `num1` receberá o valor de `a` e `num2` o valor de `b`.

### Parâmetro opcional

Caso você queria que um parâmetro seja opcional basta colocar ele entre colchetes `[ ]` na assinatura da função

```dart
void main(){//definição da função main
	
	print(diga('Patrick')); //Mensagem enviada por Patrick	
	print(diga('Patrick', 12345678)); //Mensagem enviada por Patrick do numero 12345678

}

// função com um parametro opcional
String diga(String nome, [int? telefone]){ 
	var result = 'Mensagem enviada por $nome';
	if(telefone != null){// se o parametro opcional for passado retorna uma msg usando ele
		return '$result do numero $telefone';
	}
	return result;
}
```

No código acima definimos o `telefone` como opcional, e na nossa função tratamos os dois casos, caso ele seja passado e caso não, um detalhe para se lembrar aqui, quando uma variável for usada como parâmetro opcional, ela será `nullable`, ou seja, pode ser `null` ou pode conter um valor. Para isso usamos o `?` após o tipo da variável. 

Também é possível usar de valores `default` para os parâmetros, para isso basta colocar um `=` após o nome do parâmetro e o valor padrão que ele deve ter.

Deste modo, é possível alterar o tipo de `int?` para `int`, removendo o `nullable` e consequentemente remover o `if` da nossa função. 

```dart
void main(){
  construirCasa(6); // Foi construída uma casa com 6 portas.
  construirCasa(); // Foi construída uma casa com 4 portas.
}

// função com um parametro opcional
void construirCasa([int quantidadePortas = 4]) {
  print('Foi construída uma casa com $quantidadePortas portas.');
}
```

Perceba que se passarmos nossos parâmetros em outra ordem diferente da definida no assinatura da função ( o que está entre os parênteses da nossa função ), teremos um erro, ja que o primeiro parâmetro é uma `string` e estaremos passando um `int` e vice versa.

Para isso no dart nós temos as funções com parâmetros nomeados.

### Parâmetros nomeados

As funções com parâmetros nomeados são bem interessantes, para chamar elas você tem que dizer em que parâmetro da assinatura da função você quer que o seu valor seja colocado, por padrão os parâmetros nomeados já são opcionais, vamos ver um exemplo.

```dart
void main(){//definição da função main
	
	print(diga(nome: 'Patrick')); //Mensagem enviada por Patrick	
	print(diga(nome: 'Patrick', telefone: 12345678)); //Mensagem enviada por Patrick do numero 12345678
	print(diga(telefone: 12345678, nome: 'Patrick')); //Mensagem enviada por Patrick do numero 12345678
}

// função com um parametro opcional
String diga({String? nome, int? telefone}){ 
	var result = 'Mensagem enviada por $nome';
	if(telefone != null){// se o parametro opcional for passado retorna uma msg usando ele
		return '$result do numero $telefone';
	}
	return result;
}
```

Percebeu algo diferente ? 

Na nossa assinatura da função ( o que está entre os parênteses) também colocamos entre chaves `{ }`, é dessa forma que demonstramos que os parâmetros serão nomeados.

Nossa chamada da função também mudou, agora temos que dizer explicitamente em qual parâmetro vamos colocar nossos dados. Na nossa função criamos o parâmetro nome, então na nossa chamada passaremos o dado assim `diga(nome: 'Seu Nome');` e como estamos especificando para qual parâmetro nosso valor vai podemos chamar na ordem que quisermos, note que o terceiro `print`  inverte a ordem, e antes tínhamos um erro quando fazíamos isso.

Como por padrão estes valores são opcionais, existe um modo de obrigar que eles sejam passados, para isso basta colocar um `required` antes do tipo do parâmetro, como no exemplo abaixo.

```dart
void main(){//definição da função main

  print(diga(nome: 'Patrick', telefone: 12345678)); //Mensagem enviada por Patrick do numero 12345678
  print(diga(telefone: 12345678, nome: 'Patrick')); //Mensagem enviada por Patrick do numero 12345678
  print(diga(nome: 'Patrick')); // gera erro, dizendo que o parâmetro 'telefone' é obrigatório
  print(diga(telefone: 12345678)); // gera erro, dizendo que o parâmetro 'nome' é obrigatório
}

// função com um parametro opcional obrigatório
String diga({required String nome, required int telefone}){
  var result = 'Mensagem enviada por $nome';
  return '$result do numero $telefone';
}
```

<p align="center">
  <a href="06-EstruturasDeRepeticao.md">
    <img src="../../4noobsAssets/anterior.svg" height=35>
  </a>
</p>
