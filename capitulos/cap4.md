# Capítulo 4: Manipulação de Exceções

A manipulação de exceções é uma parte fundamental da programação para lidar com situações excepcionais e erros. Neste capítulo, exploraremos como manipular exceções em Dart e as melhores práticas para tratamento de erros. Vamos começar!

## 4.1 Exceções em Dart

Em Dart, uma exceção é uma ocorrência anormal que interrompe o fluxo normal de execução do programa. Quando ocorre uma exceção, o programa procura um bloco de código responsável por tratar a exceção ou, se não encontrar, encerra a execução e exibe uma mensagem de erro.

Existem várias exceções predefinidas em Dart, como `Exception`, `Error`, `RangeError`, `TypeError` e muitas outras. Você também pode criar suas próprias exceções personalizadas estendendo a classe `Exception` ou `Error`.

## 4.2 Bloco try-catch

Em Dart, usamos blocos `try-catch` para capturar e tratar exceções. Um bloco `try` contém o código que pode gerar uma exceção, enquanto o bloco `catch` especifica o código a ser executado caso uma exceção seja lançada.

Aqui está um exemplo básico de uso de blocos `try-catch` em Dart:

```dart
void main() {
  try {
    // Código que pode gerar uma exceção
    int resultado = 10 ~/ 0; // Divisão por zero
    print('Resultado: $resultado');
  } catch (e) {
    // Tratamento da exceção
    print('Ocorreu um erro: $e');
  }
}
```

Neste exemplo, estamos tentando dividir o número 10 por zero, o que gera uma exceção `IntegerDivisionByZeroException`. Dentro do bloco `catch`, capturamos a exceção e exibimos uma mensagem de erro.

## 4.3 Cláusula finally

Além do bloco `try` e `catch`, podemos usar a cláusula `finally` para especificar um código que sempre será executado, independentemente de uma exceção ter sido lançada ou não. O bloco `finally` é opcional e segue o bloco `try-catch`.

Aqui está um exemplo de uso da cláusula `finally`:

```dart
void main() {
  try {
    // Código que pode gerar uma exceção
    int resultado = 10 ~/ 2;
    print('Resultado: $resultado');
  } catch (e) {
    print('Ocorreu um erro: $e');
  } finally {
    print('Finalizando o programa');
  }
}
```

Neste exemplo, estamos dividindo o número 10 por 2, o que não gera uma exceção. O bloco `finally` será executado após o bloco `try-catch`, independentemente de uma exceção ter sido lançada ou não.

## 4.4 Clausula on

Em Dart, também temos a opção de usar a cláusula `on` em um bloco `catch` para especificar o tipo de exceção que desejamos capturar e tratar. Isso é útil quando queremos lidar com diferentes tipos de exceções de maneiras diferentes.

Aqui está um exemplo de uso da cláusula `on`:

```dart


void main() {
  try {
    // Código que pode gerar uma exceção
    int resultado = 10 ~/ 0; // Divisão por zero
    print('Resultado: $resultado');
  } on IntegerDivisionByZeroException {
    print('Erro: Divisão por zero não é permitida');
  } catch (e) {
    print('Ocorreu um erro: $e');
  }
}
```

Neste exemplo, capturamos especificamente a exceção `IntegerDivisionByZeroException` usando a cláusula `on` e exibimos uma mensagem de erro personalizada.

Parabéns por concluir o capítulo 4! Agora você está familiarizado com a manipulação de exceções em Dart. Continue praticando e aplicando esses conceitos em seus programas para lidar com exceções de maneira adequada e garantir a robustez de seu código.