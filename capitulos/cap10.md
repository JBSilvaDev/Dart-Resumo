# Capítulo 10: Bibliotecas e Pacotes

As bibliotecas e pacotes são componentes fundamentais no desenvolvimento de aplicativos em Dart. Neste capítulo, exploraremos como criar, usar e compartilhar bibliotecas e pacotes em seus projetos. Vamos começar!

## 10.1 O que são Bibliotecas?

Em Dart, as bibliotecas são coleções de código que fornecem funcionalidades reutilizáveis. Elas nos permitem organizar e modularizar nosso código, tornando-o mais legível e fácil de manter. O Dart SDK já inclui várias bibliotecas padrão que oferecem recursos e funcionalidades para uma ampla variedade de casos de uso.

Para usar uma biblioteca em seu código, você precisa importá-la. Aqui está um exemplo de como importar a biblioteca `dart:math` para usar funções matemáticas:

```dart
import 'dart:math';

void main() {
  print(sqrt(25)); // Imprime a raiz quadrada de 25
}
```

Neste exemplo, usamos a função `sqrt()` da biblioteca `dart:math` para calcular a raiz quadrada de 25.

## 10.2 O que são Pacotes?

Pacotes são coleções de bibliotecas, arquivos e recursos relacionados que podem ser distribuídos e reutilizados em projetos Dart. Eles fornecem uma maneira conveniente de compartilhar e utilizar código entre projetos.

Os pacotes são gerenciados pelo sistema de gerenciamento de pacotes do Dart, conhecido como Pub. O Pub permite que você pesquise, instale e gerencie pacotes de forma fácil e eficiente.

Para usar um pacote em seu projeto, você precisa adicioná-lo como uma dependência no arquivo `pubspec.yaml` e executar o comando `pub get` para baixar as dependências. Aqui está um exemplo de como adicionar o pacote `http` como dependência:

```yaml
dependencies:
  http: ^0.13.0
```

Depois de adicionar a dependência, execute o comando `pub get` no terminal para baixar o pacote.

## 10.3 Publicando seus Pacotes

Se você desenvolver um pacote em Dart que deseja compartilhar com a comunidade, pode publicá-lo no repositório de pacotes do Dart, o Pub.dev. O Pub.dev é um diretório online que hospeda pacotes Dart para que outros desenvolvedores possam descobrir, usar e contribuir.

Para publicar um pacote, você precisa criar uma conta no Pub.dev e seguir as diretrizes de publicação. Certifique-se de fornecer uma descrição clara, uma documentação abrangente e um versionamento adequado para o seu pacote.

Parabéns por concluir o capítulo 10! Agora você entende como trabalhar com bibliotecas e pacotes em Dart. Continue explorando as bibliotecas padrão e aproveite os pacotes disponíveis para aumentar sua produtividade e reutilizar código em seus projetos.