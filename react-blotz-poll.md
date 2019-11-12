# React.js Интервью Вопросы и ответы

![React-logo](img/react-bliz-50.jpg)

## 1. Что такое React.js?
React js - это библиотека JavaScript с открытым исходным кодом, созданная Facebook для создания сложных интерактивных интерфейсов в веб-приложениях и мобильных приложениях.

---

## 2. Каковы особенности React.js?
Основные характеристики React перечислены ниже:

1. Виртуальный DOM: он использует виртуальный DOM вместо реального DOM.
2. Рендеринг на стороне сервера: используется рендеринг на стороне сервера (SSR).
3. Однонаправленный: следует за однонаправленным потоком данных или связыванием данных.
4. Компоненты: используются повторно используемые компоненты пользовательского интерфейса.

---

## 3. Как установить React.js с помощью приложения Create React App?
**Шаг 1**: Во-первых, установите создатель приложения реакции.
Для Windows:
```
>> npm install -g create-react-app
```
Для Linux и Mac:
```
>> sudo npm install -g create-react-app
```

**Шаг 2**: Теперь создайте свой проект с помощью приложения реакт.
```
>> create-react-app myFirstReactProject
```

**Шаг 3**: Теперь перейдите в папку проекта и запустите ваше приложение / проект.
```
>> cd myFirstReactProject
>> npm start
```
Примечание. Вы можете использовать другой менеджер пакетов, например, `yarn` и т. д.

---

## 4. В чем разница между NPM и NPX?

NPM: A node package manager -  менеджер пакетов node

NPX:  A npm package runner -  запскающий npm-пакеты

---

## 5. Как указать порт для запуска проекта, основанного на Create-React-App?
Есть два метода:

1. Переменная среды
2. package.json

Если вы не хотите устанавливать **environment variable**, другой вариант - изменить сценарии, которые являются частью вашего `package.json`

Для  Windows:
```
>> "start": "set PORT=3006 && react-scripts start"
```
Для Linux & Mac:
```
>> "start": "PORT=3006 react-scripts start"

OR

>> "start": "export PORT=3006 react-scripts start"
```

---

## 6. Что такое `props` в React?
Props - это входные данные для компонентов. Это отдельные значения или объекты, содержащие набор значений, которые передаются компонентам при создании с использованием соглашения об именах, аналогичного атрибутам HTML-тегов. Вы можете передавать `props` из родительского компонента в дочерний компонент.

---

## 7. Что такое состояние - `state` в React?

>Состояние компонента - это объект, который содержит некоторую информацию, которая может измениться за время существования компонента.

```js
class Message extends React.Component {
  constructor(props) {
    super(props)
	
    this.state = {
      message: 'Welcome to React.js Interview Questions.'
    }
  }

  render() {
    return (
      <div>
        <h1>{this.state.message}</h1>
      </div>
    )
  }
}
```

---

## 8. В чем разница между состоянием - `state`  и реквизитом - `props`?
`Props` - это свойства, реквизиты, передаваемые от родительского к дочернему компоненту, тогда как состояние - `state` управляется внутри самого компонента подобно переменным, объявленным внутри функции.

---

## 9. Что такое конструктор? и какова его главная цель?

>Метод `constructor ()` вызывается только один раз во время начальной визуализации.

В React.js конструктор используется для:

* Инициализирующие значения - `props` и `state`.
* Привязка методов обработчика событий к экземпляру.

```js
import React, { Component } from 'react';
class myComponent extends Component{
  constructor(props) {
    super(props);
    // Don't call this.setState() here!
    this.state = { counter: 0 };
    this.handleClick = this.handleClick.bind(this);
  }
}
```

Примечание:

1. Конструктор вызывается только один раз за полный жизненный цикл компонента.
2. Конструктор - это единственное место, где вы должны назначить `this.state` напрямую. В других методах жизненного цикла React вы должны использовать `this.setState ()`.
3. Если вы реализуете конструктор, вы должны вызывать `super (props)` перед любым другим оператором. если вы не будете вызывать `super (props)`, `this.props` будет неопределенным в компоненте, что может привести к ошибкам.

---

## 10. Обязательно ли определять конструктор для компонента React?
Нет, это не обязательно. Т.е., если вы не инициализируете состояние и не привязываете методы, вам не нужно реализовывать конструктор для вашего компонента React.

---

## 11. Разница между конструктором и `getInitialState`?
`getInitialState` принадлежит ES5, а конструктор -`constructor` - ES6.

>`getInitialState` используется с `React.createClass`, а конструктор используется с `React.Component`.

ES5
```js
var MyComponent = React.createClass({
  getInitialState() {
    return { /* initial state */ };
  },
});
```

ES6
```js
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = { /* initial state */ };
  }
}
```

---

## 12. Реакт ES6 Конструктор - `constructor` и ключевое слово - `super`?
1. Нужно ли вызывать super () внутри конструктора?
Ответ ДА, если вы хотите установить свойство или получить доступ к нему внутри конструктора, вам нужно вызвать `super ()`.

```js
class MyComponent extends React.Component {
	constructor(props){
		this.name = "Hello"; // Error-  'this' is not allowed before super()
	}
	render() {
		return(
		 <p> Name: { this.props.name }</p>
		);
	}
}
```
Итак, теперь мы понимаем, что нам нужно вызвать super (), если нам нужно использовать `this` внутри конструктора.

2. Как обстоят дела с `super()` vs `super(props)`?
`props` будет не определен внутри конструктора класса, если вы не будете вызывать `super (props)`.

```js
class MyComponent extends React.Component {
	constructor(props){
		super();
		this.state = {
		 name: this.props.name; 
     // here props would be undefined.
		};
	}
	render() {
		return(
		 <p> Name: { this.state.name }</p>
		);
	}
}
```

```js
class MyComponent extends Component {
	constructor(props){
		super(props);
		this.state = {
			name: this.props.name; 
		};
	}
	render() {
		return(
		 <p> Name: { this.state.name }</p>
		);
	}
}
```

---

## 13. В чем разница между `super()` и `super(props)`?
Если вы хотите получить доступ к `this.props` внутри конструктора, вам нужно передать параметр `props` в ключевое слово `super`.

---

## 14. Использует ли React.js HTML?
Нет, он использует JSX.

---

## 15. Что такое JSX?

>JSX означает JavaScript XML.

React.js использует JSX для шаблонов вместо обычного JavaScript. Использовать его не обязательно, однако ниже приведены некоторые плюсы, которые поставляются с JSX.

* JSX позволяет разработчикам размещать HTML-код внутри JavaScript.

* JSX является типобезопасным, поэтому большинство ошибок можно обнаружить во время компиляции.

```js
class App extends React.Component {
  render() {
    return(
      <div>
        <p>{'Welcome to React Js Interview Questions'}</p>
      </div>
    )
  }
}
```

---

## 16. Как писать выражения и комментарии в JSX?
**Выражения JavaScript**: Мы используем `{}` для написания выражений в коде JSX.

**Комментарии**: при написании комментариев мы должны использовать фигурные скобки `{/*comment*/}` или `{//comment}`

```js
render() {
  return (
	 <div>
		<h1>Expression & Comments in JSX:</h1>
		<p>5 is equeal to {2+3}</p>
		{//Single line Comment...}
		{/*Multi-line comment...*/}
	 </div>
  );
}
```

---

## 17. Почему браузеры не могут читать JSX?
Браузеры могут только читать объекты JavaScript, но JSX не является обычным объектом JavaScript. Вот почему браузеры не могут читать JSX. Для чтения JSX в браузерах в первую очередь нам необходимо преобразовать код JSX в объект JavaScript с помощью Babel, а затем передать его браузеру.

---

## 18. Соседние элементы JSX должны быть заключены в тег?
Если вы передадите несколько тегов, то реакт выдаст ошибки, например: Adjacent JSX elements be wrapped in an enclosing tag - говорит нам о том, что смежные элементы в Реакт, должны быть обернуы в один тег.

Посто помните, что реакт возвращает все в одном теге!

Ошибка:
```js
class HelloWorld extends React.Component{
 render(){
	return(
	 <h1>React.js Interview Questions</h1>
	 <p>Hello, You can not use multiple tags like this</p>
	)
 }
}
```
В приведенном выше примере, если вы передадите данные в метод рендеринга, как указано выше, это приведет к ошибке.

Причина: потому что метод `render ()` принимает только JSX, поэтому вы можете передать все в одном теге. Таким образом, следующий пример является правильным способом написать это.

```js
class HelloWorld extends React.Component{
 render(){
	return(
	<div classname="App">
		<h1>React.js Interview Questions</h1>
		<p>Hello, You can use multiple tags like this wrapped into a single tag.</p>
	</div>
	)
 }
}
```

---
---
# Intermediate

## 19. 
