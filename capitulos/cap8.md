Capítulo 8: Desenvolvimento de Aplicações Mobile com Dart

O Dart é uma linguagem de programação que também pode ser usada para o desenvolvimento de aplicativos móveis modernos e multiplataforma. Neste capítulo, vamos explorar como utilizar o Dart para criar aplicativos mobile eficientes e com excelente desempenho. Vamos começar!

8.1 Configuração do Ambiente

Antes de começar a desenvolver aplicativos mobile com Dart, é necessário configurar o ambiente de desenvolvimento. Certifique-se de ter o Dart SDK instalado em seu sistema e um editor de código compatível com o Dart, como o Visual Studio Code.

Para desenvolver aplicativos mobile com Dart, utilizaremos o framework Flutter. Certifique-se de ter o Flutter SDK instalado e configurado em seu ambiente.

8.2 Criação de Widgets

Em Flutter, a construção da interface de usuário é feita por meio da composição de widgets. Widgets são componentes reutilizáveis que representam elementos da interface, como botões, campos de texto, imagens, entre outros.

Aqui está um exemplo básico de criação de um widget em Dart:

```dart
import 'package:flutter/material.dart';

class MeuWidget extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Container(
      child: Text('Meu Widget'),
    );
  }
}
```

Neste exemplo, criamos um novo widget chamado `MeuWidget` que exibe o texto 'Meu Widget' em um `Container`. O método `build()` é obrigatório e define a estrutura do widget.

8.3 Navegação entre Telas

Em aplicativos mobile, a navegação entre telas é uma parte essencial. Flutter oferece uma variedade de recursos para facilitar a navegação entre telas, como o `Navigator` e as rotas (routes).

Aqui está um exemplo básico de navegação entre telas em Dart:

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MaterialApp(
    home: TelaInicial(),
    routes: {
      '/tela2': (context) => Tela2(),
    },
  ));
}

class TelaInicial extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Tela Inicial'),
      ),
      body: Center(
        child: RaisedButton(
          child: Text('Ir para Tela 2'),
          onPressed: () {
            Navigator.pushNamed(context, '/tela2');
          },
        ),
      ),
    );
  }
}

class Tela2 extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Tela 2'),
      ),
      body: Center(
        child: RaisedButton(
          child: Text('Voltar'),
          onPressed: () {
            Navigator.pop(context);
          },
        ),
      ),
    );
  }
}
```

Neste exemplo, definimos duas telas (`TelaInicial` e `Tela2`). Ao pressionar um botão na `TelaInicial`, utilizamos o `Navigator` para navegar para a `Tela2`. Na `Tela2`, há um botão que, quando pressionado, utiliza o `Navigator` para retornar à tela anterior.

8.4 Interação com APIs

Na maioria dos aplicativos móveis, é necessário interagir com APIs para buscar dados ou enviar informações. Em Dart, podemos realizar chamadas a APIs utilizando bibliotecas como o `http

` ou o `dio`.

Aqui está um exemplo básico de uma chamada a uma API em Dart:

```dart
import 'package:flutter/material.dart';
import 'package:http/http.dart' as http;

void main() {
  runApp(MaterialApp(
    home: MyApp(),
  ));
}

class MyApp extends StatelessWidget {
  Future<void> buscarDados() async {
    var url = 'https://api.exemplo.com/dados';
    var resposta = await http.get(url);

    if (resposta.statusCode == 200) {
      // Processa os dados da resposta
      print('Dados: ${resposta.body}');
    } else {
      print('Erro na requisição. Código: ${resposta.statusCode}');
    }
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Meu App'),
      ),
      body: Center(
        child: RaisedButton(
          child: Text('Buscar Dados'),
          onPressed: () {
            buscarDados();
          },
        ),
      ),
    );
  }
}
```

Neste exemplo, utilizamos a biblioteca `http` para realizar uma chamada GET a uma API. O método `buscarDados()` é assíncrono e faz a chamada à API. Em seguida, processamos a resposta verificando o código de status.

Parabéns por concluir o capítulo 8! Agora você está pronto para desenvolver aplicativos mobile com Dart e Flutter. Continue explorando e criando aplicativos incríveis, aproveitando todo o potencial dessa poderosa combinação de tecnologias.