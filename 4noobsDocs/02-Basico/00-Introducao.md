# 00 - Introdução
---

## 1 - Extensão

Os arquivos de código em dart usam a extensão `.dart` ( previsível ).

## 2 - Compilação

Para compilar seu programa em dart basta estar no mesmo diretório do arquivo que você quer rodar e digitar no terminal

```bash
dart nomeDoArquivo.dart
```

## 3 - Exemplo de código em dart

Aqui está um pequeno exemplo de um hello world em dart.

```dart
// Define uma função.
printInteger(int umNumero) {
  print('O número é $umNumero.'); // Print no console.
}

// Aqui é onde o programa começa a executar
main() {
  var numero= 42; // Declaraçaõ e inicialização de uma variavel.
  printInteger(numero); // Chamada de uma função.
}
```

<p align="center">
  <a href="../01-Ambiente/3-AmbienteOnline.md">
    <img src="../../4noobsAssets/anterior.svg" height=35>
  </a>
  <a href="01-Sintaxe.md">
    <img src="../../4noobsAssets/proximo.svg" height=35>
  </a>
</p>