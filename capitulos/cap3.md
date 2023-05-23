# Capítulo 3: Programação Orientada a Objetos

A programação orientada a objetos é um paradigma amplamente utilizado em Dart. Neste capítulo, exploramos os conceitos fundamentais da programação orientada a objetos, como herança, encapsulamento, polimorfismo, interfaces e mixins.

## 3.1 Herança

A herança permite criar classes que herdam características de outras classes existentes. Em Dart, a herança é realizada utilizando a palavra-chave `extends`. Aqui está um exemplo de como criar uma classe que herda de outra classe:

```dart
class Animal {
  String nome;

  void fazerBarulho() {
    print('O animal faz barulho!');
  }
}

class Cachorro extends Animal {
  void fazerBarulho() {
    print('O cachorro late!');
  }
}

void main() {
  Cachorro cachorro = Cachorro();
  cachorro.fazerBarulho(); // Saída: O cachorro late!
}
```

## 3.2 Encapsulamento

O encapsulamento é um conceito importante na programação orientada a objetos, que envolve a proteção e ocultação dos detalhes internos de uma classe. Em Dart, podemos utilizar modificadores de acesso para controlar o acesso aos membros de uma classe.

Existem três modificadores de acesso em Dart:

- `public`: não há nenhum símbolo específico para representar o modificador de acesso público. Todos os membros de uma classe são públicos por padrão.

- `private`: utiliza o prefixo `_` para indicar que um membro é privado e só pode ser acessado dentro da própria classe.

- `protected`: não há um modificador de acesso protegido em Dart. No entanto, podemos usar o modificador `_` como uma convenção para indicar que um membro é protegido e só deve ser acessado pela classe e suas subclasses.

```dart
class Pessoa {
  String nome;       // Público
  int _idade;        // Privado
  double _altura;    // Privado (convenção de proteção)

  void _exibirDetalhes() {
    print('Nome: $nome, Idade: $_idade, Altura: $_altura');
  }

  void exibirInformacoes() {
    _exibirDetalhes();
  }
}

void main() {
  Pessoa pessoa = Pessoa();
  pessoa.nome = 'João';
  pessoa._idade = 30;
  pessoa._altura = 1.75;

  pessoa.exibirInformacoes(); // Saída: Nome: João, Idade: 30, Altura: 1.75
}
```

## 3.3 Polimorfismo

Polimorfismo é a capacidade de um objeto ser tratado de várias formas, dependendo do contexto. Em Dart, o polimorfismo é alcançado através da sobrescrita de métodos e do uso de classes e interfaces abstratas. Vejamos um exemplo:

```dart
abstract class Animal {
  void fazerBarulho();
}

class Cachorro extends Animal {
  void fazerBarulho() {
    print('O cachorro late!');
  }
}

class Gato extends Animal {
  void fazerBarulho() {
    print('O gato mia!');
  }
}

void fazerAnimalBarulho(Animal animal) {
  animal.fazerBarulho();
}

void main() {
  Animal cach

orro = Cachorro();
  Animal gato = Gato();

  fazerAnimalBarulho(cachorro); // Saída: O cachorro late!
  fazerAnimalBarulho(gato);     // Saída: O gato mia!
}
```

## 3.4 Interfaces e Mixins

Interfaces e mixins são mecanismos que permitem compartilhar comportamentos entre diferentes classes em Dart. Uma interface define um conjunto de métodos que uma classe deve implementar, enquanto um mixin permite adicionar funcionalidades a uma classe sem herança direta.

Vejamos um exemplo de uso de interfaces e mixins em Dart:

```dart
class Voador {
  void voar() {
    print('Voando!');
  }
}

class Pato implements Voador {
  void voar() {
    print('O pato está voando!');
  }
}

mixin Nadador {
  void nadar() {
    print('Nadando!');
  }
}

class Golfinho with Nadador {
  // Classe Golfinho agora possui o comportamento de Nadador
}

void main() {
  Pato pato = Pato();
  pato.voar(); // Saída: O pato está voando!

  Golfinho golfinho = Golfinho();
  golfinho.nadar(); // Saída: Nadando!
}
```

Parabéns por concluir o Capítulo 3! Neste capítulo, você aprendeu sobre herança, encapsulamento, polimorfismo, interfaces e mixins. Esses conceitos são fundamentais para a programação orientada a objetos em Dart. Continue praticando e explorando esses conceitos à medida que avançamos nos próximos capítulos.