# Часто задаваемые вопросы на интервью по ES6

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

* а). Let и Const ключевые слова
* b). Arrow functions - стрелочные функции
* c). Template Literals - шаблонные литералы
* d). Object Literals - литералы объекта
* e). Default Parameters - параметры по умолчанию
* f). Destructuring Assignment - деструктурирующее присваивание
* g). Rest and Spread Operators - операторы rest и spread
* h). Modules, Classes, Iterators, Generators in ES6 - Модули, классы, итераторы и генераторы
* i). Promises in ES6 -Обещания
* j). Support for Map/Set & WeakMap/WeakSet 

---

## a). `let` и `const`:
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

## b). Функции стрелки:
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

## c). Template literals:
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

## d). Object literals:
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

## e). Default Parameters:
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

## f). Destructuring Assignment:
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

## g). REST and Spread operator:
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

## h). Class In ES6:

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

## i). Promise:

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

## j). Map:
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

## 8. Разница между функцией стрелки и обычной функцией в JavaScript?
Существуют следующие различия между функцией стрелки и обычной (обычной) функцией:

**1. Syntax:**
И Стрелка, и Нормальная (Обычная) функция имеют разный синтаксис.

```js
//Normal Function:

let func = function myFunc(params){ 
  // body of the function 
}; 

OR

function myFunc(params){ 
  // body of the function 
}; 
```

```js
//Arrow Function:

let func = (params) => { 
  // body of the function 
}; 
```

**2. Использование `this` ключевого слова:**

>В функциях Arrow нет привязки `this`

В отличие от обычных функций, функции стрелок не имеют своего собственного `this`.

```js
let myFunc = { 
	name: "Full Stack Tutorials", 
	arrowFunc:() => { 
		console.log(`Welcome to, ${this.name}`); 
    // no 'this' binding 
	}, 
	regFunc(){	 
		console.log(`Welcome to, ${this.name}`); 
    // 'this' binding works 
	} 
}; 
myFunc.arrowFunc(); 
myFunc.regFunc(); 
```

**3. Используя `new` ключевое слово:**
Функции со стрелками нельзя использовать как конструктор с `new`, это вызовет ошибку.

```js
let myFunc = () => {};
let func = new myFunc(); 
// Uncaught TypeError: myFunc is not a constructor
```

**4. Наличие объекта аргументов:**
Функции стрелок не имеют своих собственных объектов аргументов. Следовательно, arguments - это просто ссылка на аргументы внутренней области.

**5. Использование свойства прототипа:**
Функции стрелок не имеют свойства прототипа.

```js
let myFunc = () => {};
console.log(myFunc.prototype); 
// undefined
```

---

## 9. Как бы вы фильтровали массив объектов в ES6?

```javascript
var testArray = [{"name":"Jai",  "age": 26},
              {"name":"Shiv",  "age": 22},
              {"name":"Anuj", "age": 5 },
              {"name":"Jenny", "age": 20 }];
var data = testArray.filter(person => person.age > 18); 
//Filters the Array of Objects to condition set
console.log(data);
/*
0:{name: "Jai", age: 26}
1:{name: "Shiv", age: 22}
2:{name: "Jenny", age: 20}
length:3
*/
```

---

## 10. Что вы подразумеваете под IIFE - Immediately Invoked Function Expressions (выражениями с немедленным вызовом функций)?
Выражения IIFE или немедленно вызванные функции - это выражения, которые выполняются сразу же после его создания. IIFEs используются, чтобы избежать чрезмерного использования глобального пространства имен, потому что все переменные, которые используются внутри IIFE, не могут быть просмотрены вне его области. Другими словами, IIFE - это шаблоны проектирования, также известные как самоисполняющиеся анонимные функции (Self Executing Anonymous Functions), поскольку они выполняются самостоятельно.

---

## 11. Объясните, почему следующее не работает как IIFE. Что нужно изменить, чтобы правильно сделать его IIFE?

```js
function foo(){ }();
```
IIFE расшифровывается как выражения для немедленного вызова функций (Immediately Invoked Function Expressions). Парсер JavaScript читает `function foo () {} ();` as `function foo () {}` и `();` где первая часть - это объявление функции, а вторая (пара скобок) - попытка вызова функции, но имя функции не указано, поэтому он выбрасывает `Uncaught SyntaxError: Unexpected token` Неожиданный токен ).

Вот два способа исправить это, которые включают добавление дополнительных скобок: `(function foo () {}) ()` и `(function foo () {} ())`. Эти функции не отображаются в глобальной области видимости, и вы можете даже опустить ее имя, если вам не нужно, чтобы она ссылалась на саму себя внутри тела.

Вы также можете использовать оператор `void`: `void function foo () {} ();`. К сожалению, с таким подходом есть одна проблема. Оценка данного выражения всегда не определена - `undefined`, поэтому, если ваша функция IIFE возвращает что-либо, вы не можете ее использовать. Пример:

```js
// Don't add JS syntax to this code block to prevent Prettier from formatting it.
const foo = void
function bar() {
    return 'foo';
}();

console.log(foo); // undefined
```

---

## 12. Объясните мотивацию использования Simbols в ES6.
Символы - `Simbols` представляют собой особый вид объекта, недавно добавленный в шестую версию ECMAScript, который можно использовать в качестве уникального имени свойства в объектах. Использование Symbol вместо String (как это было в предыдущих версиях) позволяет программисту использовать разные модули, которые могут создавать свойства, которые не будут проблематичными друг для друга. Другим огромным преимуществом Символов является то, что они могут быть приватными, и к определенным свойствам не может получить доступ ни один пользователь или разработчик, не имеющий прямого доступа к `Simbols`. Они состоят из функции, которую можно использовать для создания разных символов, которые могут работать по-разному. Но у них нет буквального синтаксиса, в отличие от других примитивов JavaScript.

---

## 13. Объясните преимущества использования spread syntax (синтаксиса распространения) в ES6. Чем он отличается от остального синтаксиса?
Что касается кодирования в функциональной парадигме, использование spread syntax в ES6 может оказаться весьма полезным. Spread syntax может быть легко использован для создания копий массивов или объектов. Использование распространенного синтаксиса в программе не требует использования `Object.create`, `slice` или какой-либо библиотечной функции. Spread syntax широко используется в проектах Redux и rx.js.

С другой стороны, функция синтаксиса `rest` в ES6 используется для передачи произвольного числа аргументов функции. Это также можно рассматривать как сокращение в программировании на JavaScript. Rest syntax может рассматриваться как противоположность Spread syntax. Он берет данные и помещает их в массив вместо распаковки данных. В дополнение к этому, он работает подходящим образом в аргументах функций, массивах, а также в назначениях деструктурирования объектов.

>Примечание. Этот вопрос задается почти во всех интервью ES6.

---

## 14. Какая разница между ES6 class  ES5 function constructors?

| ES6 class	| ES5 Function Constructors |
|:----------|:--------------------------|
| Класс ES6 в основном выполняет работу по определению нового объекта и добавлению функций к его прототипу. | ES5 Конструкторы функций работают и выглядят одинаково, но основное различие наблюдается, когда разработчик использует свойство `Inheritance`. |
| Их можно рассматривать как основу синтаксиса для функций конструктора. |  Они могут быть выполнены только с помощью нового оператора. |
| Класс ES6 позволяет разработчикам создавать объекты с помощью оператора `new`. | Конструкторы функций ES5 фокусируются на том, как создаются объекты. |
| Они также гарантируют разработчику, что `this` ключевое слово, которое в основном используется внутри класса, относится только к объекту, который создается разработчиком. | Конструктор функций ES5 фокусируется на реализации кода создания многократно используемых объектов. Любая функция может быть использована в качестве конструктора. |

---

## 15. Разница между `.call` и `.apply`?

| .call |	.apply |
|:------|:-------|
| `.call` используется для вызова функций, и первый параметр станет значением этого значения в функции, созданной разработчиком. | `.apply` также используется для вызова функций, но он принимает массив аргументов. Этот массив работает как следующий аргумент, и функция работает таким образом. |
| `.call` используется для вызова метода, который принимает объект-владелец в качестве аргумента. | Метод `.apply` используется для написания методов. Эти методы могут быть использованы для нескольких объектов. |
| Он принимает два параметра, а именно `objectInstance` и `arguments`. |  Он принимает два параметра, а именно `objectInstance` и `arrayofArguments`. |
| `.call` принимает несколько аргументов, разделенных запятыми. | `.apply` принимает несколько аргументов с помощью массива аргументов. |

---

## 16. Объясните причину использования классов ES6.
Классы ES6 оказались очень полезными для разработчиков. Некоторые из основных видов использования классов ES6:

* Классы ES6 имеют более простой и менее подверженный ошибкам синтаксис.
* Что касается настройки иерархий наследования, то ES6 считается наилучшим вариантом, поскольку он использует новый синтаксис со старым синтаксисом, который минимизирует ошибки и облегчает процесс.
* Классы ES6 помогают защитить разработчиков от неправильного использования новых функций с помощью функции конструктора. Это одна из самых распространенных ошибок, возникающих у разработчиков при использовании нового оператора. Классы устраняют эту ошибку, заставляя конструктор генерировать исключение, если это оказывается недопустимым объектом для конструктора.
* Классы также помогают вызывать метод, имеющий версию прототипа. Эта версия намного проще с новым синтаксисом ES6, чем старые версии.

---

## 17. Что такое generator (генератор) в JavaScript?
С запуском ES6 появился новый способ работы с функциями и итераторами. Они называются генераторами. Генератор - это не что иное, как функция, которая может остановиться в тот момент, когда пользователь прикажет ему сделать это, а затем продолжить работу только с того места, где он остановился. Другими словами, генератор имеет свойства функции, но также работает как итератор. Он не работает как другие строки кода, которые необходимо заполнить для выполнения.

Генераторы работают по модели «от завершения к завершению», которая облегчает разработчикам компиляцию программы. Генераторы также могут быть определены как специальный класс функций, которые работают для упрощения задачи кодирования итераторов в программе. Это производит последовательность результатов, а не производит единственное значение. Это позволяет разработчику создавать серию значений одновременно.

>Это очень важный вопрос интервью для javascript ES6.

---

## 18. Определить  temporal dead zone  (временную мертвую зону) в ES6.
Временная мертвая зона  temporal dead zone - может быть определена как промежуток времени, который существует между временем, связанным с привязкой переменной к ее объявлению в программе. Временная мертвая зона существует, так что программные ошибки можно легко идентифицировать как переменную, которая может быть доступна до ее объявления. Также для правильной работы `const` можно использовать временную мертвую зону. Он также используется для защиты JavaScript, который в основном является механизмом, используемым во время выполнения.

---

## 19. Что такое `spread` -параметр распространения, `default` - по умолчанию и `rest` параметры?
**Spread Operator** - Пожертвовано «...» и сопровождается переменной. Например, синтаксис оператора распространения может выглядеть следующим образом: - «`... X`». Операторы распространения манипулируют объектами и массивами, что является основной причиной его использования в ES6. Он используется для копирования свойства одного объекта другому.
Spread оператор разбивает коллекцию на отдельные аргументы функции, это позволяет вызывать функцию, которая принимает три параметра, с одним параметром.
```js
const day = [2015, 10, 12];
const dayOff = new Date(...day);
let firstArray=[4,5,6]
let secondArray=[1,2,3,...firstArray] // [1,2,3,4,5,6]
```

**Default Operator** (Оператор по умолчанию) - для инициализации функции с использованием значений по умолчанию используется оператор по умолчанию. Значением параметра может быть что угодно - число, функция или null.
Синтаксис похож на другие языки: argumentName = someValue.
`function join(arr,separator=','){ return arr.join(separator)}`

**Rest Parameter** . Этот оператор используется для восстановления всех аргументов, необходимых для вызова функции. Это позволяет нам разделять элементы, принадлежащие к разным категориям. Параметр `rest` позволяет объединить параметры в общий параметр массива.
```js
function push(arr,elem,...otherElems){
  arr.push(elem);
  
  if(otherElems.length){
    otherElems.forEach(e=>push(arr,e))
  }
}
```

---

## 20. Что такое `classes` и `proxies`?
**Class** - Вы можете легко использовать шаблоны с объявлением класса на основе ООП. Он легко работает с конструкторами, поддерживает доступ к базовому классу, наследование и статические методы. ООП относится к объектно-ориентированному программированию.

**Proxies**. С помощью прокси вы можете создавать объекты и размещать объекты с огромным разнообразием поведения. Прокси могут также помочь в профилировании и регистрации.
Прокси-это объект, который перехватывает попытки доступа к другому объекту и может изменять их. Синтаксис:
```js
let proxy = new Proxy(target, handler)
```

---

## 21. Когда я должен использовать функции стрелки в ES6?
Сейчас я использую следующее правило для функций в ES6 и более поздних версиях:

* Используйте `function` в глобальной области видимости и для свойств `Object.prototype`.
* Используйте `class` для конструкторов объектов.
* Используйте `=>` везде в осальном.

Зачем использовать функции стрелок почти везде?

* **Scope safety** - Безопасность области: Когда функции стрелок используются последовательно, все гарантированно будет использовать тот же объект `thisObject`, что и корневой. Если даже один стандартный вызов функции смешивается с кучей функций со стрелками, есть вероятность, что область видимости испортится.
* **Compactness** - Компактность: функции со стрелками легче читать и писать. (Это может показаться самоуверенным, поэтому я приведу несколько примеров далее).
* **Clarity** - Ясность: когда почти все является функцией стрелки, любая обычная функция немедленно выделяется для определения области видимости. Разработчик всегда может найти следующий более высокий оператор функции, чтобы увидеть, что это за `thisObject.`

---

## 22. Когда НЕ следует использовать функции стрелок в ES6? Назовите три или более случаев.
Функции стрелок НЕ должны использоваться:

* Когда мы хотим использовать поднятие функции (hoisting) - так как функции стрелок являются анонимными.
* Когда мы хотим использовать `this` / `arguments` в функции - поскольку функции стрелок не имеют собственных аргументов / arguments, они зависят от своего внешнего контекста.
* Когда мы хотим использовать именованную функцию - в качестве стрелки функции анонимны.
* Когда мы хотим использовать функцию в качестве конструктора - функции стрелок не имеют своих собственных.
* Когда мы хотим добавить функцию как свойство в литерал объекта и использовать в нем объект - так как мы не можем получить к нему доступ (которым должен быть сам объект).


---

## 23. Объясните разницу между `Object.freeze ()` и `const`.
`const` и `Object.freeze` - это две совершенно разные вещи.

`const` применяется к привязкам («переменным»). Он создает неизменяемую привязку, то есть вы не можете назначить новое значение привязке.

```js
const person = {
    name: "Leonardo"
};
let animal = {
    species: "snake"
};
person = animal; // ERROR "person" is read-only
```
`Object.freeze` работает со значениями и, более конкретно, со значениями объектов. Это делает объект неизменным, то есть вы не можете изменить его свойства.
```js
let person = {
    name: "Leonardo"
};
let animal = {
    species: "snake"
};
Object.freeze(person);
person.name = "Lima"; //TypeError: Cannot assign to read only property 'name' of object
console.log(person);
```
---

## 24. Объясните Prototype Design Pattern.
_Prototype Pattern_  Шаблон прототипа создает новые объекты, но вместо создания неинициализированных объектов он возвращает объекты, инициализированные значениями, которые он скопировал из объекта-прототипа или образца. _Prototype Pattern_  также называется шаблоном Properties (Properties pattern).

Примером использования _Prototype Pattern_ является инициализация бизнес-объектов со значениями, которые соответствуют значениям по умолчанию в базе данных. Объект-прототип содержит значения по умолчанию, которые копируются во вновь созданный бизнес-объект.

Классические языки редко используют Properties pattern, но JavaScript, являющийся языком-прототипом, использует этот шаблон при конструировании новых объектов и их прототипов.

---

## 25. Не могли бы вы сравнить использование Module Pattern против Constructor / Prototype pattern?
Module Pattern - Шаблон модуля обычно используется для пространства имен, где у вас будет один экземпляр, выступающий в качестве хранилища для группировки связанных функций и объектов. Это другой вариант использования, из которого хорошо подходит прототипирование. Они на самом деле не конкурируют друг с другом; вы можете с радостью использовать оба вместе (например, поместить функцию-конструктор внутри модуля и объявить `new MyNamespace.MyModule.MyClass (arguments))`.

Функции-конструкторы и прототипы являются одним из разумных способов реализации классов и экземпляров. Они не совсем соответствуют этой модели, поэтому обычно вам нужно выбрать конкретную схему или вспомогательный метод для реализации классов с точки зрения прототипов.

---

## 26. Каковы предпосылки использования в ES6 `WeakMap` ? 
`WeakMaps` предоставляют возможность расширять объекты извне, не мешая сборке мусора. Всякий раз, когда вы хотите расширить объект, но не можете, потому что он запечатан - или из внешнего источника - можно применить WeakMap.

`WeakMaps` доступны только для ES6 и выше. WeakMap - это набор пар ключ-значение, где ключ должен быть объектом.

```js
var map = new WeakMap();
var pavloHero = {
    first: "Pavlo",
    last: "Hero"
};
var gabrielFranco = {
    first: "Gabriel",
    last: "Franco"
};
map.set(pavloHero, "This is Hero");
map.set(gabrielFranco, "This is Franco");
console.log(map.get(pavloHero)); //This is Hero
```
Интересным аспектом `WeakMaps` является тот факт, что он содержит слабую ссылку на ключ внутри карты. Слабая ссылка означает, что если объект будет уничтожен, сборщик мусора удалит всю запись из `WeakMap`, освободив таким образом память.

---

## 27. В чем разница между ES6 `Map` и `WeakMap`?
Они оба ведут себя по-разному, когда объект, на который ссылаются их ключи / значения, удаляется. Давайте возьмем следующий пример кода:

`var map = new Map ();`

`var weakmap = new WeakMap ();`

```js
(function() {
    var a = {
        x: 12
    };
    var b = {
        y: 12
    };

    map.set(a, 1);
    weakmap.set(b, 2);
})()
```

Вышеупомянутый IIFE выполняется, и мы больше не можем ссылаться на `{x: 12}` и `{y: 12}`. Сборщик мусора идет вперед и удаляет указатель ключа `b` из «WeakMap», а также удаляет `{y: 12}` из памяти. Но в случае «Map» сборщик мусора не удаляет указатель из «Map», а также не удаляет `{x: 12}` из памяти.

WeakMap позволяет сборщику мусора выполнять свою задачу, но не Map. С картами, написанными вручную, массив ключей будет хранить ссылки на ключевые объекты, предотвращая их сборку мусора. В собственных WeakMaps ссылки на ключевые объекты хранятся «слабо - _weakly_», что означает, что они не предотвращают сборку мусора в случае, если не будет другой ссылки на объект.

---

## 28. Можете ли вы привести пример функции каррирования (curry function) и почему этот синтаксис дает преимущество?
Карринг (каррирование) - это шаблон, в котором функция с более чем одним параметром разбивается на несколько функций, которые при последовательном вызове будут накапливать все необходимые параметры по одному. Этот метод может быть полезен для облегчения чтения и написания кода, написанного в функциональном стиле. Важно отметить, что для функции, которую нужно каррировать, она должна начинаться как одна функция, а затем разбиваться на последовательность функций, каждая из которых принимает один параметр.

```js
function curry(fn) {
  if (fn.length === 0) {
    return fn;
  }

  function _curried(depth, args) {
    return function(newArgument) {
      if (depth - 1 === 0) {
        return fn(...args, newArgument);
      }
      return _curried(depth - 1, [...args, newArgument]);
    };
  }

  return _curried(fn.length, []);
}

function add(a, b) {
  return a + b;
}

var curriedAdd = curry(add);
var addFive = curriedAdd(5);

var result = [0, 1, 2, 3, 4, 5].map(addFive); // [5, 6, 7, 8, 9, 10]
```

---

## 29. Как «заморозить» ("deep-freeze") объект в JavaScript?
Если вы хотите убедиться, что объект глубоко заморожен, вы должны создать рекурсивную функцию для замораживания каждого свойства, имеющего тип объекта:

Без глубокой заморозки (Without deep freeze):

```js
let person = {
    name: "Leonardo",
    profession: {
        name: "developer"
    }
};
Object.freeze(person); // make object immutable
person.profession.name = "doctor";
console.log(person); //output { name: 'Leonardo', profession: { name: 'doctor' } }
```
C deep freeze:
```js
function deepFreeze(object) {
    let propNames = Object.getOwnPropertyNames(object);
    for (let name of propNames) {
        let value = object[name];
        object[name] = value && typeof value === "object" ?
            deepFreeze(value) : value;
    }
    return Object.freeze(object);
}
let person = {
    name: "Leonardo",
    profession: {
        name: "developer"
    }
};
deepFreeze(person);
person.profession.name = "doctor"; // TypeError: Cannot assign to read only property 'name' of object

```

---
---