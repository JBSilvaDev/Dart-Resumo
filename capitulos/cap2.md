# Capítulo 2: Conceitos Básicos

Neste capítulo, vamos explorar os conceitos básicos do Dart. Você aprenderá sobre a sintaxe do Dart, variáveis e tipos de dados, estruturas de controle, funções e manipulação de coleções como listas, mapas e conjuntos. Vamos começar!

## 2.1 Sintaxe do Dart

A sintaxe do Dart é bastante similar a outras linguagens de programação, o que a torna fácil de aprender. Aqui estão alguns elementos importantes da sintaxe do Dart:

- Declaração de variáveis: Para declarar uma variável, utilizamos a palavra-chave `var`, seguida pelo nome da variável e seu tipo. Por exemplo:

```dart
var nome = 'João';
```

- Comentários: Comentários são trechos de texto que são ignorados pelo compilador e servem para documentar o código. Existem dois tipos de comentários em Dart: comentários de linha única (iniciados com `//`) e comentários de múltiplas linhas (iniciados com `/*` e terminados com `*/`).

- Função `main()`: Assim como no capítulo anterior, a função `main()` é o ponto de entrada do programa em Dart. É onde a execução do programa começa.

## 2.2 Variáveis e Tipos de Dados

Em Dart, podemos declarar variáveis com diferentes tipos de dados. Aqui estão alguns dos tipos de dados mais comuns:

- Números: `int` para números inteiros e `double` para números de ponto flutuante.

```dart
int idade = 30;
double altura = 1.75;
```

- Strings: representam sequências de caracteres e são declaradas entre aspas simples ou duplas.

```dart
String nome = 'Maria';
String sobrenome = "Silva";
```

- Booleanos: `true` ou `false`, que representam os valores lógicos verdadeiro e falso, respectivamente.

```dart
bool estaChovendo = true;
bool estaSol = false;
```

- Listas: representam coleções ordenadas de elementos.

```dart
List<int> numeros = [1, 2, 3, 4, 5];
List<String> nomes = ['João', 'Maria', 'Carlos'];
```

- Mapas: representam coleções de pares chave-valor.

```dart
Map<String, String> telefones = {
  'João': '123456789',
  'Maria': '987654321',
};
```

## 2.3 Estruturas de Controle

As estruturas de controle são utilizadas para controlar o fluxo de execução do programa. Dart possui estruturas de controle comuns, como `if`, `else`, `switch`, `for`, `while`, entre outras. Aqui está um exemplo de utilização do `if`:

```dart
if (idade >= 18) {
  print('Você é maior de idade.');
} else {
  print('Você é menor de idade.');
}
```

## 2.4 Funções

As funções são blocos de código que podem ser chamados e executados em diferentes partes do programa. Em Dart, podemos definir funções da seguinte maneira:

```dart
int soma(int a, int b) {
  return a + b;
}

void main() {
  int resultado = soma(5, 3);
  print('A soma é $resultado');
}
```

No

 exemplo acima, temos uma função chamada `soma` que recebe dois parâmetros do tipo `int` e retorna a soma desses valores. A função `main()` chama a função `soma` e imprime o resultado.

## 2.5 Trabalhando com Listas, Mapas e Conjuntos

Dart oferece recursos poderosos para trabalhar com coleções. Aqui estão alguns exemplos:

- Acessando elementos de uma lista:

```dart
List<int> numeros = [1, 2, 3, 4, 5];
print(numeros[0]); // Saída: 1
```

- Adicionando elementos a uma lista:

```dart
List<String> nomes = ['João', 'Maria'];
nomes.add('Carlos');
print(nomes); // Saída: [João, Maria, Carlos]
```

- Acessando valores de um mapa:

```dart
Map<String, String> telefones = {
  'João': '123456789',
  'Maria': '987654321',
};
print(telefones['João']); // Saída: 123456789
```

- Verificando se um conjunto contém um elemento:

```dart
Set<int> numeros = {1, 2, 3, 4, 5};
print(numeros.contains(3)); // Saída: true
```

Este foi apenas um vislumbre dos conceitos básicos do Dart. Nos próximos capítulos, vamos nos aprofundar em tópicos mais avançados, como programação orientada a objetos, manipulação de exceções, programação assíncrona e muito mais. Continue aprendendo e praticando para se tornar um mestre em Dart!