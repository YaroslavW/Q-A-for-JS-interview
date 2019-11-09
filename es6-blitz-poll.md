# # Часто задаваемые вопросы на интервью по ES6

<p align="center">
<img src="img/es6-blitx-50.jpg" alt="logo-es6-blitz-poll">
</p>

## 1. Что такое ES6?
* ES6 также известен как ECMAScript 2015.
* ES6 или ECMAScript 2015 является 6-ым основным выпуском ECMAScript.
* Если ваш браузер не поддерживает ES6, вы можете написать совместимый код ES6, используя Babel и Webpack.
* ES10 (ECMAScript 2019) - это последняя версия ECMAScript.

---

## 2. Что такое ECMAScript?
ECMAScript - это спецификация, определенная в стандарте ECMA-262 для создания языка сценариев общего назначения.

---

## 3. Что такое JavaScript?
Язык сценариев общего назначения, соответствующий спецификации ECMAScript.

---

## 4. Что такое JavaScript Engine?
Программа или интерпретатор, который понимает и выполняет код JavaScript.

Самый популярный движок JavaScript:

* Google Chrome - V8 // Fastest JavaScript Engine
* Mozilla FireFox - SpiderMonkey
* Microsoft Edge - Chakra

---

## 5. Что такое Babel?
* Babel - один из самых популярных javascript-транспортеров.
* Babel в основном используется для преобразования кода ES6 + (ECMAScript 2015+) в обратно совместимую версию JavaScript, которая может быть запущена старыми механизмами JavaScript.

---

## 6. Что такое Webpack?
* Webpack позволяет запускать среду, в которой работает Babel.
* Webpack - это пакет модулей javascript с открытым исходным кодом, который принимает модули с зависимостями и генерирует статические ресурсы, представляющие эти модули.

**Преимущества использования Webpack:**

1. Он объединяет несколько ваших модулей и упаковывает их в один файл `.js`.
2. Он поставляется с интегрированным сервером разработки. Небольшое экспресс-приложение для локальной разработки. Вы просто включаете один тег Javascript, указывающий на сервер, например `localhost: 8080 / assets / bundle.js`, и получаете бесплатное обновление кода и управление ресурсами.

---

## 7. Перечислите некоторые новые функции в ES6?

**Новые функции в ES6:**
Лучшие 10 функций ES6, которые должен знать каждый разработчик JavaScript.

1. Let и Const ключевые слова
2. Arrow functions - стрелочные функции
3. Template Literals - шаблонные литералы
4. Object Literals - литералы объекта
5. Default Parameters - параметры по умолчанию
6. Destructuring Assignment - деструктурирующее присваивание
7. Rest and Spread Operators - операторы rest и spread
8. Modules, Classes, Iterators, Generators in ES6 - Модули, классы, итераторы и генераторы
9. Promises in ES6 -Обещания
10. Support for Map/Set & WeakMap/WeakSet 

---

## 1. `let` и `const`:
**`Const` Ключевое слово**:
* Ключевое слово `const` используется для определения констант в ES6.
  это также известно как неизменяемые переменные.
* Значение константы не может быть изменено путем переназначения, и оно не может быть повторно объявлено.

```js
const MY_CONST = "Javascript ES6 Interview Questions";
console.log(MY_CONST); 
//Javascript ES6 Interview Questions
MY_CONST = "ES6 Interview Questions";
console.log(MY_CONST); 
// Uncaught TypeError: Присвоение постоянной переменной,
// потому что мы не можем переназначить новое значение константе
```

В случае `Object` и `Array` мы можем добавить в него новые элементы

```js
const myObject = {'name': 'Full Stack Tutorials'};
// Если вы попытаетесь 
// перезаписать / переназначить / переопределить объект,
//  выдается ошибка.

myObject = {'name': 'Full Stack Tutorials'}; 
//Uncaught TypeError: Присвоение постоянной переменной.
myObject = {'fullname': 'Full Stack Tutorials'}; 
//Uncaught TypeError: Присвоение постоянной переменной..

// Поскольку ключи объектов не защищены,
//  приведенный ниже код будет успешно выполнен.
myObject.name = 'Anonymous User'; 
// Вы можете использовать Object.freeze (), 
// чтобы сделать объект неизменным

const myArray = ["Javascript", "Node.js", "React.js"];
// Можно помещать элементы в массив
myArray.push("jQuery");
// Но присвоение нового массива той же переменной 
// приведет к ошибке.

myArray = ["jQuery"]; 
//Uncaught TypeError: Присвоение постоянной переменной.
```

`Object.freeze()`
>`Object.freeze` работает со значениями и делает объект неизменным.

*`Object.freeze ()` принимает объект в качестве аргумента и возвращает тот же объект, что и неизменный объект*

Как только вы заморозили объект, вы не можете изменять, добавлять или удалять свойства объекта, но вы можете назначить другой экземпляр.

```js
const myObject = {'name': 'Full Stack Tutorials'};
Object.freeze(myObject);
myObject.name = 'Anonymous User'; 
// выдает ошибку в строгом режиме
console.log(myObject.name); 
// Выведет: Full Stack Tutorials
```

**`let` ключевое слово**:
ES6 представляет новое ключевое слово `let`, которое позволяет нам объявлять локальные переменные в области видимости блока.

Позволяет вам объявлять переменные, которые ограничены по видимости блоком, оператором или выражением, в котором они используются.

```js
let a = 10;
funtion testMe(){
	let a = 20;
	console.log(a); // 20
}
console.log(a); // 10

```

---

## 2. Функции стрелки:
* Функция стрелки имеет более короткий синтаксис, чем обычная функция.
* В функции Arrow `this` ключевого слова не существует.

```js
(param1, param2, …, paramN) => { 
//statements or code
}
```

```js
//in ES5
var sum = function(a, b) {
return a + b; 
};
console.log(sum(10,40)); // 50

----------------------------
//in ES6
var total = (x, y) => {
	return (x + y);
}
console.log(total(20,30)); // 50
```

---

## 3. Template literals:
ES6 представляет новые и простые в использовании строковые шаблоны с заполнителями для переменных.

* Шаблонные литералы заключены в обратную галочку (``).
* Вы можете использовать многострочные строки.
* Вы можете использовать новый синтаксис `$ {variable_name}` внутри строки, помеченной галочкой.
* До ES6 это называлось Template Strings.

```js
//Пример-1

var num1 = 10;
var num2 = 20;
console.log(`The sum of ${num1} and ${num2} is ${num1 + num2}.`); 

//Выведет: The sum of 10 and 20 is 30

//Пример-2

var TempBody = `Hello Users! Your are reading about ES6 Features,
    In ES6, you are implementing Template Literals.
    Let me show you the sum of ${num1} and ${num2} is ${num1 + num2}. 
	Hope you have understood the concept of Template Literals.`;
	
console.log(TempBody);
```

---

## 4. Object literals:
Объектный литерал JavaScript представляет собой разделенный запятыми список пар имя-значение, заключенных в фигурные скобки.

```js
var myObject = {
    title: 'ES6 Interview Questions and Answers',
    topic: 'Object Literals',
    status: true,
	myFunction: () => {
		// Блок кода
	}
};
```

---

## 5. Default Parameters:
Параметры функции по умолчанию позволяют инициализировать именованные параметры с некоторыми значениями по умолчанию, если значение не передано или не определено.

```js
//3-й параметр имеет значение по умолчанию ноль.

let addNumbers = (a, b, c = 0) => {
  return a + b + c;
}

console.log(addNumbers(1, 2, 2)); //5
console.log(addNumbers(5, 20)); //25
```

---

## Destructuring Assignment:
Деструктурирующее присваивание - это специальный синтаксис, который позволяет вам «распаковывать» массивы или объекты в кучу переменных, так как иногда они более удобны.

```js
// у нас есть массив с именем, отчеством и фамилией
let arr = ["Full", "Stack", "Tutorials"]

// destructuring assignment
let [first_name, middle_name, last_name] = arr;

console.log(first_name); // Full
console.log(middle_name); // Stack
console.log(last_name); // Tutorials
```

---

## 7. REST and Spread operator:
Оператор спреда, или три точки, (…) - это новый оператор, введенный в ES6. Это позволяет расширять итерируемый (например, Array) на составляющие его элементы.

```js
const t = [1, 2, 3];

const s = [...t, 4, 5, 6];

console.log(s); 
// [1, 2, 3, 4, 5, 6];
```

**Пример: - Удалить дубликаты элементов из массива с помощью ES6 Set?**

>Объект Set позволяет хранить уникальные значения любого типа, будь то примитивные значения или объект

Вот одна строка для удаления дубликатов из массива. (ES6, конечно!)

```js
const numbers = [1, 2, 3, 4, 5, 5, 5, 5, 5, 5];

function removeDuplicates(array) {
  return [...new Set(array)];
}
console.log(removeDuplicates(numbers));
 // [1, 2, 3, 4, 5]
```

Набор - `Set` был введен в ES6 и похож на наборы, с которыми мы сталкиваемся в математике: они не могут иметь дубликаты. После этого мы просто конвертируем `Set` обратно в массив, используя оператор распространения - `...`.

---

## 8. Class In ES6:

```js
class User{
    constructor(name, age) {
        this.name  = name;
        this. age = age;
    }
   getUserDetails() {
        console.log(this.name + " is " + this. age + " years old!");
    }
}

var userObj = new User("Full Stack Tutorials", 5);
console.log(userObj.getUserDetails());

//Вывод: Full Stack Tutorials is 5 years old!
```
**Генераторы**

Генератор - это функция, которая может остановиться на полпути, а затем продолжить с того места, где остановилась. Короче говоря, генератор выглядит как функция, но ведет себя как итератор.

```js
function* process() {
    console.log('Start process 1');
    console.log('Pause process2 until call next()');

    yield;

    console.log('Resumed process2');
    console.log('Pause process3 until call next()');

    yield;

    console.log('Resumed process3');
    console.log('End of the process function');
}

let _process = process();
```
**yield**:
* Ключевое слово `yield` просто помогает приостановить и возобновить функцию в любое время асинхронно.
* Кроме того, это помогает вернуть значение из функции генератора.

**в использовании**
* Ленивая оценка -Lazy evaluation
* Бесконечные последовательности - Infinite sequences
* Асинхронные потоки управления - Asynchronous control flows

---

## 9. Promise:

>Обещания используются для обработки асинхронных операций в JavaScript.

Обещание - это объект, который может быть возвращен синхронно из асинхронной функции.

Обещание преодолеть проблему ада обратного вызова - **callback hell**.

**Promise States**:
* Fulfilled:будет вызвано `onFulfilled ()` (например, `resolve()` - разрешено был вызван)
* Rejected: отклонено - вызывается `onRejected ()` (например, вызывается `reject ()`).
* Pending: ожидание - исходное состояние, не выполнено и не отклонено.

Promise Consumers: then, catch, finally

```js
var promise = new Promise(function(resolve, reject) { 
const A = "fullstacktutorials"; 
const B = "fullstacktutorials"
if(A === B) { 
	resolve(); 
} else { 
	reject(); 
} 
}); 

promise. 
	then(function () { 
		console.log('Success, Your promise has been resolved successfully'); 
	}). 
	catch(function () { 
		console.log('Something went wrong!'); 
	}); 
```

---

## 10. Map:
Объект Map представляет собой простую карту  - ключ / значение.

Любое значение (как объекты, так и примитивные значения) может использоваться в качестве ключа или значения. Синтаксис [ключ, значение].

```js
hash = new Map()
hash.set("FullStackTutorials", "Learn Full Stack Tutorials free Online, Javascript ES6 Interview Questions")
hash.set(1, 200);

console.log(hash); 
//Output: Map(2) {"FullStackTutorials" => 
// "Learn Full Stack Tutorials free Online, Javascript ES6 Interview Questions",
//  1 => 200}

```

---

## Разница между функцией стрелки и обычной функцией в JavaScript?