# 06 - Estruturas de repetição

As vezes queremos fazer algo de maneira repetida, com por exemplo um programa para contar de 1 a 10, podemos fazer usando varias vezes o `print` porém isso fica muito repetitivo e caso agora você queira contar de 11 a 20 terá que mudar em todos os 10 prints.

Para isso temos as estruturar de repetição, um código que cria um loop que vai rodar quantas vezes você quiser.

---

## For

O primeiro deles é o for, inicialmente ele pode parecer estranho, mas vamos tentar aqui deixar o mais detalhado possível.

Logo abaixo temos um código que imprime os números de 1 a 10 usando for.

```dart
for (int contador = 1; contador < 11; contador++) {
    print(contador);
}

/* saida
1
2
3
4
5
6
7
8
9
10
*/
```

Pode parecer meio complicado, mas já passamos por todos esses assuntos usados no for, então caso algum desses símbolos não esteja claro você pode voltar e dar uma lida novamente. Vamos lá pra explicação.

Passo a passo:

1. colocamos o for com os parênteses `( )` onde ele recebera a como queremos que o nosso loop funcione, e as chaves `{ }` para por dentro o que nós queremos que ele faça a cada repetição.
2. Se você notar dentro dos parênteses nós podemos separar seu conteúdo em 3 partes , essa separação é feita pelo `;`
   - Primeira parte `int contador = 1` : aqui definimos o inicio no nosso loop, ou seja, criamos uma variável, chamamos ela de contador e colocamos o valor 1 dentro dela.
   - Segunda parte `contador < 11` : Aqui nós definimos quando o nosso loop dele parar, ele faz essa validação toda vez que o contador aumentar. Nesse caso quando a nossa variável `contador` for igual ou maior que 11 o nosso for irá parar.
   - Terceira parte `contador++` : Essa conta irá rodar toda vez que chegarmos ao fim do corpo do for, ou seja, depois que rodar tudo que está dentro das chaves `{ }`. Ela ira aumentar nosso contador em 1.
3. No corpo do nosso for temos o código que ira imprimir o valor atual do nosso contador.

Lembra lá do inicio quando falamos de listas ? Então, o for é muito útil para lidar com aquele dado, vamos olhar melhor como isso funciona, de uma olhada na lista abaixo.

```dart
var lista1 = [ 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 ];
```

Para imprimir todos os dados da lista acima podemos fazer simplesmente usando 10 `print( );`mas se você perceber isso fica complicado caso você tenha muitos dados na lista e a cada numero adicionado tem que fazer mais um `print`. Fazendo isso estamos fazendo na mão varias vezes a mesma coisa, porque não usar um loop ? É ai que o for se encaixa perfeitamente, vamos ver como:

```dart
//Nós ja falamos anteriormente que para contar os itens de uma lista
//temos que comentar contando do 0 lembra? Então vamor fazer um loop para isso

var lista = [ 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 ];

for(int i = 0; i < lista.length; i++){
	print(lista[i]);
}
/*
1
2
3
4
5
6
7
8
9
10
*/
```

Vamos a uma explicação. Você prestou atenção na segunda parte do nosso for ? Viu esse `lista.length`? Então, quando estamos trabalhando com listas temos algumas funções que fazem umas coisas legais pra gente, no caso desse `.length` ele nos retorna o tamanho da nossa lista, nesse caso ele vai retornar o número 10, e como as posições das listas começam a ser contadas pela 0 a última posição no nosso caso será a 9. Lembra também como pegar um valor que esteja em uma posição específica da lista ? Então, como o nosso `i` passa por todas as posições da nossa lista usamos ele para fazer nosso `print`, dessa forma as cada repetição do loop ele irá printar a próxima posição, até chegar na ultima, quando ele irá parar.

É importante pontuar que nós precisamos definir muito bem quando o nosso loop for parar, pois no caso de listas se você tentar pegar uma posição que não exista nós teremos um erro dizendo que a posição que você pediu não existe.

## While

O while também faz loops como o for, porém com ele é necessário ter um pouco de cuidado pois caso você defina errado quando ele deve parar ele pode entrar em um loop inifinito e travar o seu programa. Dito isso, vamos ao exemplo de contar de 1 a 10:

```dart
int contador = 1;
while( contador < 11){
	print(contador);
	contador++;
}
```

É importante notar duas coisas, a primeira é que a variável que ele irá verificar já precisa existir, não é possível criar ela dentro dos parênteses do `while`. A segunda é que no final você deve fazer o incremento do seu contador, pois caso não faça se você prestar atenção irá perceber que para o `while` o contador SEMPRE será menor do que 11, então ele ira rodar até você forçar o fechamento do seu programa.

<p align="center">
  <a href="05-EstruturasCondicionais.md">
    <img src="../../4noobsAssets/anterior.svg" height=35>
  </a>
  <a href="07-Funcoes.md">
    <img src="../../4noobsAssets/proximo.svg" height=35>
  </a>
</p>
