---
title: "Flux: Entendendo a arquitetura \_\U0001F389"
path: /blog/introducing-tina-grande
date: '2020-12-06T00:00:00.000Z'
type: post
authors:
  - alessandro-gentil
draft: false
hero:
  image: ../images/react.jpeg
  large: false
  overlay: true
---

> **Flux** é uma arquitetura usada pelo Facebook junto com o framework React.

Mas, talvez seja mais fácil começar falando o que Flux não é e com o que ele não deve ser comparado para facilitar o entendimento!

Flux não é um framework ou biblioteca.

Comparemos ele com a arquitetura MVC.

No lugar de dividir a aplicação entre Model, View e Controller, com Flux há a sugestão de dividir em Stores, Dispatcher, Views, Action/Action Creators.

Talvez já tenha visto algumas imagens como essa quando estava tentando entender MVC.

E geralmente vinham com uma explicação de cada item, exatamente como farei agora:

- Views – A interface do usuário, renderiza e cuida das interações com o usuário, de onde partirá os callbacks para criar as actions.
- Actions – Eventos que passam os dados para o dispatcher.
- Dispatcher – Recebe os dados e envia para todos os stores registrados para ouvir àquela action.
- Stores – Recebe as actions contendo os dados e emite eventos, eventos estes que irão atualizar os dados dos states, fazendo com que as views sejam renderizadas novamente.

```js
function getTodoState() {
  return {
    allTodos: TodoStore.getAll(),
    areAllComplete: TodoStore.areAllComplete()
  };
}

var TodoApp = React.createClass({

  getInitialState: function() {
    return getTodoState();
  },

// ...
```

## Contributing

Contribute by reporting bugs, requesting features or submiting improvements! We made this for you and would ❤️ any feedback or contributions to make **Tina Grande** better for everyone.
