Capítulo 3: Programação Orientada a Objetos

A programação orientada a objetos é um paradigma de programação amplamente utilizado em Dart. Neste capítulo, vamos explorar os conceitos fundamentais da programação orientada a objetos em Dart. Você aprenderá sobre herança, encapsulamento, polimorfismo, interfaces e mixins. Vamos começar!

3.1 Herança

Herança é um dos pilares da programação orientada a objetos. Ela permite criar classes que herdam características de outras classes existentes. Em Dart, a herança é realizada utilizando a palavra-chave `extends`. Aqui está um exemplo de como criar uma classe que herda de outra classe:

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

Neste exemplo, temos a classe `Animal` que possui uma propriedade `nome` e um método `fazerBarulho()`. A classe `Cachorro` herda da classe `Animal` utilizando `extends` e substitui o método `fazerBarulho()`. Ao criar uma instância da classe `Cachorro` e chamar o método `fazerBarulho()`, o resultado será "O cachorro late!".

3.2 Encapsulamento

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

Neste exemplo, temos a classe `Pessoa` com os membros `nome`, `_idade` e `_altura`. O membro `_exibirDetalhes()` é um método privado que só pode ser acessado dentro da própria classe. O método `exibirInformacoes()` chama

 o método `_exibirDetalhes()` para exibir as informações da pessoa. Observe que o acesso direto aos membros privados fora da classe é possível em Dart, mas é uma prática desencorajada.

3.3 Polimorfismo

Polimorfismo é a capacidade de um objeto ser tratado de várias formas, dependendo do contexto. Em Dart, o polimorfismo é alcançado através da sobrescrita de métodos e do uso de classes e interfaces abstratas. Vamos dar uma olhada em um exemplo:

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
  Animal cachorro = Cachorro();
  Animal gato = Gato();

  fazerAnimalBarulho(cachorro); // Saída: O cachorro late!
  fazerAnimalBarulho(gato);     // Saída: O gato mia!
}
```

Neste exemplo, temos a classe abstrata `Animal` que define o método `fazerBarulho()`. As classes `Cachorro` e `Gato` estendem a classe `Animal` e implementam o método `fazerBarulho()` de forma diferente. O método `fazerAnimalBarulho()` recebe um objeto do tipo `Animal` e chama o método `fazerBarulho()`. Ao chamar o método `fazerAnimalBarulho()` com objetos `Cachorro` e `Gato`, o polimorfismo entra em ação e os métodos adequados são executados.

3.4 Interfaces e Mixins

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

Neste exemplo, a classe `Voador` define um método `voar()`. A classe `Pato` implementa a interface `Voador` e substitui o método `voar()`. A classe `Golfinho` utiliza o mixin `Nadador`, que adiciona o método `nadar()` à classe `Golfinho`.

Com o uso de interfaces e mixins, podemos criar classes que compartilham comportamentos comuns sem herança direta, promovendo a reutilização de código e tornando o código mais modular e flexível.

Parabéns por concluir

 o capítulo 3! Neste capítulo, você aprendeu sobre herança, encapsulamento, polimorfismo, interfaces e mixins. Esses conceitos são fundamentais para a programação orientada a objetos em Dart. Continue praticando e explorando esses conceitos à medida que avançamos nos próximos capítulos.