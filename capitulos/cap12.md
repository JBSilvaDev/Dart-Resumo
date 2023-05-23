# Capítulo 12: Arquitetura de Aplicativos Dart - MVC e MVVM

A arquitetura de um aplicativo desempenha um papel crucial no desenvolvimento de software. Ela define como as diferentes partes do aplicativo se relacionam e interagem entre si. Neste capítulo, exploraremos duas arquiteturas populares em Dart: MVC (Model-View-Controller) e MVVM (Model-View-ViewModel). Vamos conhecer essas arquiteturas e entender como elas podem ser aplicadas no desenvolvimento de aplicativos Dart.

## 12.1 Arquitetura MVC (Model-View-Controller)

O padrão de arquitetura MVC separa as responsabilidades do aplicativo em três componentes principais: o Model (modelo), a View (visão) e o Controller (controlador). Vamos conhecer cada um desses componentes:

- Model (Modelo): O modelo representa a camada de dados do aplicativo. Ele lida com a lógica de negócios, a manipulação dos dados e a interação com as fontes de dados, como bancos de dados ou serviços da web.

- View (Visão): A visão é responsável pela apresentação dos dados ao usuário. Ela exibe a interface do usuário e recebe as interações do usuário, encaminhando-as para o controlador.

- Controller (Controlador): O controlador atua como um intermediário entre o modelo e a visão. Ele recebe as interações do usuário da visão, processa essas interações e atualiza o modelo conforme necessário. Em seguida, ele atualiza a visão com os dados atualizados do modelo.

A arquitetura MVC promove a separação de preocupações, facilitando a manutenção e a evolução do aplicativo. Cada componente tem uma responsabilidade clara e pode ser modificado independentemente dos outros componentes.

## 12.2 Arquitetura MVVM (Model-View-ViewModel)

A arquitetura MVVM é uma variação da arquitetura MVC, introduzindo o conceito de ViewModel (Modelo de Visão). Ela também divide o aplicativo em três componentes principais: o Model, a View e o ViewModel. Vamos entender cada um desses componentes:

- Model (Modelo): O modelo desempenha o mesmo papel que na arquitetura MVC, tratando da lógica de negócios e da manipulação dos dados.

- View (Visão): A visão é responsável por exibir a interface do usuário e lidar com as interações do usuário.

- ViewModel (Modelo de Visão): O ViewModel é um intermediário entre a visão e o modelo. Ele fornece os dados e comportamentos necessários para a visão, permitindo que ela seja atualizada dinamicamente. O ViewModel também pode tratar de ações e eventos específicos da visão.

A principal diferença da arquitetura MVVM em relação ao MVC é que a visão não conhece diretamente o modelo. Em vez disso, ela se comunica com o ViewModel, que por sua vez interage com o modelo. Essa separação permite uma maior testabilidade e reutilização do código da visão.

## 12.3 Escolhendo a Arquitetura Certa

Tanto o MVC quanto o MVVM têm seus benefícios e são amplamente utilizados em aplicativos Dart. A escolha da arquitetura certa depende do tamanho e da complexidade

 do seu aplicativo, das necessidades de teste, da escalabilidade e da equipe de desenvolvimento. É importante considerar os requisitos do seu projeto antes de escolher uma arquitetura.

Ambas as arquiteturas podem ser implementadas em Dart usando estruturas e bibliotecas disponíveis, como o Flutter. Existem pacotes e frameworks que oferecem suporte específico para MVC e MVVM, facilitando a implementação e o gerenciamento dos componentes.

## Conclusão

Neste capítulo, exploramos as arquiteturas MVC e MVVM no contexto do desenvolvimento de aplicativos Dart. Ambas as arquiteturas fornecem uma estrutura sólida para a separação de responsabilidades e a organização do código. A escolha da arquitetura depende das necessidades e requisitos do seu projeto. Experimente as diferentes abordagens e encontre a que melhor se adapte ao seu estilo de desenvolvimento e ao seu aplicativo.

Parabéns por concluir o capítulo 12! Agora você está familiarizado com as arquiteturas MVC e MVVM em Dart. Use esse conhecimento para projetar e desenvolver aplicativos eficientes, escaláveis e de fácil manutenção.

***
## Exemplo de Implementação do MVC:

Modelo (Model):
```dart
class UserModel {
  String name;
  int age;

  UserModel({required this.name, required this.age});
}
```

Visão (View):
```dart
class UserView {
  void displayUserInfo(String name, int age) {
    print('Nome: $name, Idade: $age');
  }
}
```

Controlador (Controller):
```dart
class UserController {
  UserModel user;
  UserView view;

  UserController({required this.user, required this.view});

  void updateUser(String newName, int newAge) {
    user.name = newName;
    user.age = newAge;
    view.displayUserInfo(user.name, user.age);
  }
}
```

Exemplo de Uso do MVC:
```dart
void main() {
  // Criando os objetos do modelo, visão e controlador
  UserModel user = UserModel(name: 'João', age: 30);
  UserView view = UserView();
  UserController controller = UserController(user: user, view: view);

  // Atualizando os dados do usuário e exibindo as informações
  controller.updateUser('Maria', 35);
}
```

## Exemplo de Implementação do MVVM:

No padrão MVVM (Model-View-ViewModel), não há um componente chamado Controller. O ViewModel assume as responsabilidades tanto do Controller quanto do Model-View-Controller (MVC). O ViewModel age como um intermediário entre a View (Visão) e o Model (Modelo).

Modelo (Modelo):
```dart
class UserModel {
  String name;
  int age;

  UserModel({required this.name, required this.age});
}
```

Visão (View):
```dart
class UserView {
  void displayUserInfo(String name, int age) {
    print('Nome: $name, Idade: $age');
  }
}
```

ViewModel (Model-View-ViewModel):
```dart
class UserViewModel {
  UserModel user;

  UserViewModel({required this.user});

  String get userName => user.name;
  int get userAge => user.age;

  void updateUser(String newName, int newAge) {
    user.name = newName;
    user.age = newAge;
  }

  void displayUserInfo() {
    UserView view = UserView();
    view.displayUserInfo(user.name, user.age);
  }
}
```

Ex

emplo de Uso do MVVM:
```dart
void main() {
  // Criando o objeto do modelo
  UserModel user = UserModel(name: 'João', age: 30);

  // Criando o objeto do ViewModel
  UserViewModel viewModel = UserViewModel(user: user);

  // Atualizando os dados do usuário
  viewModel.updateUser('Maria', 35);

  // Exibindo as informações usando o ViewModel
  viewModel.displayUserInfo();
}
```

Exemplos de arquitetura em pastas > [aqui](./exemplo_estuturas_pastas.md)

O ViewModel é responsável por atualizar o modelo e fornecer os dados necessários para a View. A própria View é chamada a partir do ViewModel para exibir as informações atualizadas.