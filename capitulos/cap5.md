# Capítulo 5: Programação Assíncrona

A programação assíncrona desempenha um papel crucial na construção de aplicativos modernos e responsivos. Neste capítulo, exploraremos a programação assíncrona em Dart, usando Futures, Streams e async/await. Vamos começar!

## 5.1 Futures

Em Dart, um Future representa um valor que pode estar disponível agora ou no futuro. Um Future é usado para representar uma tarefa assíncrona que será concluída posteriormente. Podemos esperar (await) um Future para obter seu resultado.

Aqui está um exemplo simples de uso de um Future em Dart:

```dart
Future<String> obterDadosDaAPI() {
  return Future.delayed(Duration(seconds: 2), () {
    return 'Dados da API';
  });
}

void main() async {
  print('Início');

  String dados = await obterDadosDaAPI();
  print(dados);

  print('Fim');
}
```

Neste exemplo, a função `obterDadosDaAPI()` retorna um Future que será concluído após um atraso de 2 segundos. Na função `main()`, usamos `await` para esperar pelo resultado do Future e armazená-lo na variável `dados`. O código aguarda a conclusão do Future antes de continuar para a próxima linha.

## 5.2 Streams

Streams são sequências contínuas de eventos assíncronos em Dart. Eles são úteis para lidar com dados em tempo real, como eventos de usuário, transmissões de rede e muito mais. Podemos usar o método `listen()` para se inscrever em um Stream e receber os eventos à medida que eles ocorrem.

Aqui está um exemplo de uso de um Stream em Dart:

```dart
import 'dart:async';

void main() {
  final meuStream = Stream<int>.periodic(Duration(seconds: 1), (valor) => valor).take(5);

  meuStream.listen((valor) {
    print('Valor: $valor');
  });
}
```

Neste exemplo, criamos um Stream chamado `meuStream` que emite um valor a cada segundo. Usamos o método `listen()` para nos inscrever no Stream e receber os valores emitidos. A cada valor recebido, imprimimos o valor na saída.

## 5.3 async/await

A sintaxe async/await é uma forma mais simples e legível de lidar com tarefas assíncronas em Dart. Ela permite que o código assíncrono seja escrito de forma síncrona, facilitando a compreensão e a manutenção do código.

Aqui está um exemplo de uso de async/await em Dart:

```dart
Future<int> obterDados() async {
  await Future.delayed(Duration(seconds: 2));
  return 42;
}

void main() async {
  print('Início');

  int resultado = await obterDados();
  print('Resultado: $resultado');

  print('Fim');
}
```

Neste exemplo, a função `obterDados()` é marcada com `async` e retorna um Future<int>. Dentro da função, usamos `await` para esperar por um atraso de 2 segundos antes de retornar o valor 42. Na função `main()`, também marcada com `async`, usamos `await` para esperar pelo resultado de `obter

Dados()` antes de imprimir o resultado.

Parabéns por concluir o capítulo 5! Agora você está familiarizado com a programação assíncrona em Dart usando Futures, Streams e async/await. Continue praticando e explorando esses conceitos para criar aplicativos assíncronos eficientes e responsivos.