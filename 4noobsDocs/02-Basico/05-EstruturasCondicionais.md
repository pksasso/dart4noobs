# 05 - Estruturas condicionais

As estruturar de repetição funcionam baseadas em uma entrada, ela verifica essa entrada da forma que você programar e retorna algo dependendo do dado que entre.

## If

O if é uma das mais simples condicionais. If em inglês significa SE. Ela verifica a entrada e SE o que entrar for verdadeiro ela roda o código de dentro.

Exemplo:

```dart
String name = 'Patrick';
// SE a variavel name tiver a String 'Patrick' então rode o seguinte código
if(name == 'Patrick'){
	print('Seja bem vindo Patrick !');
}
```

Note que a validação que você pede tem que estar entre parênteses `( )` , e caso essa validação seja verdadeira ele entra no bloco de código definido pelas chaves `{ }` e roda aquele código, se a validação for falsa o programa continua sem rodar o código entre chaves `{ }`

### If Else

Caso você queira fazer algo se o o if não for verdadeiro você deve usar o else, em inglês else é SE NÃO. O else só funciona se estiver seguido do if e o seu código interno deve estar entre chaves `{ }` também.

Exemplo:

```dart
String name = 'Pedro';
// essa primeira parte é o if que ja vimos
if(name == 'Patrick'){
	print('Seja bem vindo Patrick !');
} else { //e logo após vem o else, para caso o if seja falso
	print('Usuário não reconhecido');
}

//Neste exemplo o que vai acontecer é que vai testar o if e ver que a variavel name
//não é igual a String 'Patrick', então ele vai entrar no código do else
```

## Else if

Mas e se eu quiser testar em várias vezes, e não só uma? Bem, ai temos e `else if` que fica posicionado entre o `if` e o `else` ele funciona como outras opções de `if`

exemplo:

```dart
String name = 'João';

if(name == 'Patrick'){
	print('Seja bem vindo Patrick !');
} else if(name == 'Pedro'){ // Aqui nós temos 3 opções de verificação
	print('Seja bem vindo Pedro !');
} else if(name == 'Ana'){
	print('Seja bem vinda Ana!');
} else {
	print('Usuário não reconhecido');
}
```

É legal notar que é bom deixar o `else` para caso nenhuma das opções forem verdadeiras ai o `else` roda. Você também pode colocar quantos `else if` quiser.

### Switch

Se você notar o `else if` fica meio grande né ? Tem muita coisa escrita e pode causar confusões.

Para casos assim temos o switch, que funciona de forma muito similar ao `else if`, porém com um pouco mais de organização. No exemplo abaixo farei a mesma validação feita acima mas com o `switch`

Exemplo:

```dart
String name = 'João';

switch (name){
	case 'Patrick':
		print('Seja bem vindo Patrick !');
		break;
	case 'Pedro':
		print('Seja bem vindo Pedro!');
		break;
	case 'Ana':
		print('Seja bem vinda Ana!');
		break;
	default:
		print('Usuário não reconhecido');
}
```

O `switch` recebe alguma variável que será analisada durante os seus `cases`.

O `case` verifica se o que o switch recebeu tem o mesmo valor que ele, a marcação de o que esta dentro do case é os `:` , e se você notar tem um comando novo ali, o `break` , no caso do switch ele é super importante pois com não temos chaves aqui pra cada `case` é o `break` que vai dizer que o comando acabou, se não por ele o código irá dar um erro.

No final temos um `default` que em inglês significa uma opção padrão, é ela que era rodar caso nenhum dos `cases` de certo.

## Operador Ternário

No desenvolvimento é comum de utilizarmos essas estruturas condicionais descritas anteriormente mas existe uma nova possibilidade chamada de operador ternário na qual 
quando existem apenas duas possibilidades seu uso se torna mais vantajoso comparado aos anteriores.

Sua estrutura funciona assim
```
condição? valor se for verdareiro : valor se for falso
```

Vamos pegar o exemplo citado no topico IF Else:

``
Se usuario é Patrick, 'Bem Vindo Patrick', senao 'Usuário não reconhecido'
``

Esta logica pode ser transcrita para codigo da seguinte forma:
Exemplo:

```dart
  String name = 'Patrick';
  String mensagem = ( name == 'Patrick' ? 'Seja bem vindo Patrick !' : 'Usuário não reconhecido');
  print(mensagem);

```
Veja que em nosso exemplo o codigo ficou mais limpo e foi utilizado menos linhas de codigo se comparado ao ``IF Else``


<p align="center">
  <a href="04-Operadores.md">
    <img src="../../4noobsAssets/anterior.svg" height=35>
  </a>
  <a href="06-EstruturasDeRepeticao.md">
    <img src="../../4noobsAssets/proximo.svg" height=35>
  </a>
</p>