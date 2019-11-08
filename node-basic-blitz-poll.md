# Node.Js Интервью Вопросы | Основы

## 1. Что такое Node.js?

Node.js - это кроссплатформенная среда выполнения JavaScript с открытым исходным кодом для выполнения кода JavaScript на стороне сервера.

Самый популярные движки JavaScript:

1. Google Chrome - V8 // Fastest JavaScript Engine
2. Mozilla FireFox - SpiderMonkey
3. Microsoft Edge - Chakra

---

## 2. Как установить переменные среды (environment variables) ?

Перед запуском приложения можно указать переменные среды, используя следующий синтаксис:

```
NODE_ENV=production PORT=3000 $ [runtime] [program_name]
```

Переданные значения будут находится в переменной `process.env`

---

## 3. На каком языке написан Node.js?

Node.js написан на - C, C ++, JavaScript и его автором является Райан Даль (Ryan Dahl)

---

## 4. Каковы основные характеристики Node.js?

Node.js имеет много функций, которые делают node.js более мощным.

1. **Асинхронность и управление событиями** -
   Все API библиотеки Node.js являются асинхронными, то есть неблокирующими операциями ввода-вывода.

Node.js может обрабатывать несколько одновременных запросов, это сила node.js. После того, как он завершит выполнение запроса, он запустит обратный вызов, чтобы уведомить о его завершении.

2. **Node.js работает очень быстро** -
   Node.js использует Google Chrome V8 JavaScript Runtime Engine, написанный на C ++, который компилирует код JavaScript в машинный код, что ускоряет выполнение node.js.

JavaScript Engine: это программа, которая преобразует код JavaScript в низкоуровневый или машинный код.

3. **Однопоточный, но очень масштабируемый** -
   Node.js является однопоточным, который в фоновом режиме (под капотом Node.js использует много потоков через libuv) использует несколько потоков для выполнения асинхронного кода.

Приложения Node.js используют однопотоковую модель цикла событий - **Single Threaded Event Loop Model** для обработки нескольких одновременных запросов.

Механизм Event Loop помогает серверу отвечать неблокирующим образом, в результате чего сервер становится масштабируемым, в отличие от традиционных серверов, которые создают ограниченные потоки для обработки запросов.

4. **Библиотека Node.js использует JavaScript** -
   Поскольку большинство разработчиков уже используют JavaScript. Итак, разработка в Node.js становится проще для разработчика, который уже знает JavaScript.

5. **NPM (Node Package Manager)** -
   NPM означает Node Package Manager, он позволяет нам устанавливать различные пакеты для приложения Node.js.

6. **Нет буферизации** -
   Приложения Node.js никогда не буферизуют данные. Они просто выводят данные кусками.

7. **Сообщество** -
   У Node.js очень хорошее сообщество, которое постоянно обновляет фреймворк с учетом последних тенденций в веб-разработке.

---

## 5. Что такое НПМ? Зачем нужен NPM в Node.js?

**NPM** означает **Node Package Manager**, он поставляется с node.js и позволяет нам устанавливать различные пакеты для приложений Node.js.

```js
npm install express --save
npm install lodash --save
```

---

## 6. Как проверить глобально установленные зависимости с помощью NPM?

```
npm ls -g
```

---

## 7. Что такое NVM? Какая польза от NVM в Node.js?

**NVM** расшифровывается как **Node Version Manager**. Вы можете использовать nvm для очень простого изменения версий вашего node.js, это очень полезно, если вы работаете над несколькими проектами Node.js с разными версиями и т. Д.

---

## 8. Что такое Nodemon?

Nodemon - это инструмент, который отслеживает приложения node.js на наличие изменений в исходном коде и автоматически перезапускает ваш сервер.

- Nodemon - лучший инструмент для разработки при разработке проекта node.js.
- Nodemon доступен в виде пакета NPM.
- Вы также можете установить nodemon как зависимость для разработки:

```
npm install nodemon --save-dev
```

```
nodemon [your node app]

//Example
nodemon app.js //app.js is the main file of your Node.js project.
```

---

## 9. Что такое REPL в Node.js (Read-Eval-Print Loop)?

1. REPL расшифровывается как «Read Eval Print Loop». Это простая программа, которая принимает команды, оценивает их и, наконец, печатает результаты.
2. REPL предоставляет среду, аналогичную среде оболочки Unix / Linux или оконной консоли, в которой мы можем ввести команду, а система, в свою очередь, отвечает выводом.
3. Чтобы запустить REPL (оболочка узла), откройте командную строку (в Windows) или терминал (в Mac или UNIX / Linux) и введите `node`, как показано ниже. Это изменит приглашение на `>` в Windows и MAC.

REPL позволяет легко создавать приложения CLI (интерфейс командной строки).

### REPL выполняет следующие задачи.

**READ**: Читает вводимые пользователем данные, анализирует их в структуру данных JavaScript и затем сохраняет их в памяти.

**EVAL**: выполняет структуру данных (вычисления).

**PRINT**: печатает результат, полученный после оценки команды.

**LOOP**: повторяет вышеуказанную команду, пока пользователь не нажмет **_Ctrl + C_** два раза.

Более подробно о работе с REPLв моем блоге - https://abcinblog.blogspot.com/2018/09/repl.html

---

---

# Node.Js Интервью Вопросы | Средний уровень

## 1. Что такое релизы LTS? Почему они важны?
* **LTS**: означает долгосрочную поддержку. Выпуски LTS получают все исправления критических ошибок, обновления безопасности и улучшения производительности.
* У версии LTS есть поддержка и обслуживание сообщества в течение не менее 18 месяцев, поэтому в продуктах будет полезно использовать версии Active LTS или Maintenance LTS.
* **Важность версии LTS**. Как только строка текущего выпуска становится LTS, в этот выпуск не будут добавлены новые функции или критические изменения.

---

## 2. В чем разница между LTS и стабильной версией Node.js?
* **LTS**: - Версия долгосрочной поддержки (LTS) имеет как минимум 18-месячную поддержку и обслуживание, поэтому она более стабильна и безопасна.

* **Stable**: - Текущая стабильная версия имеет 8 месяцев поддержки и обслуживания.

---

## 3. Как получить данные Post в Node.js?

```html
<form method="post" action="/">
    <input type="text" name="message">
    <input type="submit" value="Submit">
</form>
```

```js
app.use(bodyParser.urlencoded({
    extended: true
}));
app.use(bodyParser.json());

app.post("/", function (req, res) {
    console.log(req.body.message);
});
```

---

## 4. Как сделать запрос GET / Post в Node.js?
Ниже приведен простой пример запроса HTTP GET / POST в Node.js.

```javascript
//GET:

var request = require('request');

// Set the headers
var headers = {
    'Content-Type':'application/x-www-form-urlencoded'
}

// Configure the request
var options = {
    url: 'https://www.fullstacktutorials.com',
    method: 'GET',
    headers: headers,
    qs: {'message': 'Node.js Interview Questions'}
}

// Start the request
request(options, function (error, response, body) {
    if (!error && response.statusCode == 200) {
        console.log(body)
    }
})
//The above code will make a GET  request like - http://localhost:3000/?message=Node.js Interview Questions



//POST:
var request = require('request');

// Set the headers
var headers = {
    'Content-Type':'application/x-www-form-urlencoded'
}

// Configure the request
var options = {
    url: 'https://www.fullstacktutorials.com',
    method: 'POST',
    headers: headers,
    form: {'message': 'Node.js Interview Questions'}
}

// Start the request
request(options, function (error, response, body) {
    if (!error && response.statusCode == 200) {
        console.log(body)
    }
})
//Приведенный выше код сделает запрос POST, 
// например, - http: // localhost: 3000 / 
// с параметром message = Node.js Вопросы для интервью.
```

---

## 5. В чем ключевое отличие Ajax от Node.js?
Ajax (сокращение от асинхронного JavaScript и XML) - это технология на стороне клиента, часто используемая для обновления содержимого страницы без ее обновления. в то время как Node.js - среда выполнения JavaScript на стороне сервера.

---

## 6. Что такое обратный вызов в Node.js?
Обратный вызов - это функция, которая вызывается автоматически при завершении заданной задачи. Node  интенсивно использует обратные вызовы.

Пример:
```javascript
var myCallback = function(err, data) {
  if (err) throw err; // Проверьте на ошибку и throw, если она существует.
  console.log('Your Data is: ' +data); // Обработать данные.
};

var myFunc = function(callback) {
  callback(null, 'This is Callback Example in Node.js'); //Я не хочу выдавать (throw) ошибку, поэтому я передаю ноль для аргумента ошибки
};

//Вызов функции
myFunc(myCallback);
```

---

## 6. Что такое "Callback Hell" («Ад обратного вызова») и как его можно избежать?
Ад обратного вызова относится к шаблону кодирования, где существует множество вложений функций обратного вызова. Код формирует структуру, похожую на пирамиду, и его становится трудно отлаживать. Иногда это называется пирамида гибели - pyramid of doom.

Представьте себе, если вам нужно сделать обратный вызов после обратного вызова:

```javascript
getDetails(function(a){  
    getMoreDetails(a, function(b){
        getMoreDetails(b, function(c){ 
            getMoreDetails(c, function(d){ 
                getMoreDetails(d, function(e){ 
                    //and so on...
                });
            });
        });
    });
});
```

"Callback Hell" можно избежать с помощью:
1. Модульный код
2. используя обещания - `Promises`
3. используя `async / await`

---

## 7. Что такое  error first callback -  ошибка первого обратного вызова node.js?
1. Первый аргумент обратного вызова зарезервирован для объекта ошибки. Если произошла ошибка, она будет возвращена первым аргументом `err`.
2. Второй аргумент обратного вызова зарезервирован для любых успешных данных ответа. Если ошибки не произошло, для `err` будет установлено значение `null`, а данные будут возвращены во втором аргументе.

```javascript
fs.readFile('myfile.txt', function(err, data) {
// Если произошла ошибка, обработайте ее (throw etc)
if(err) {
	console.log('Error Found:' + err);
	throw err;
}
// В противном случае, вывести в консоль данные
console.log(data);
});
```

---

## 8. Как отловить - `catch` все `uncaughtException` для Node.js?
Используйте процессы `uncaughtException` и `unhandledRejection`

```javascript
process
  .on('unhandledRejection', (reason, p) => {
    console.error(reason, 'Unhandled Rejection at Promise', p);
  })
  .on('uncaughtException', err => {
    console.error(err, 'Uncaught Exception thrown');
    process.exit(1);
  });

```

---

## 9. Что такое package.json в node.js?
1. `package.json` - это файл json, который содержит всю информацию метаданных о вашем приложении node.js.
2. NPM (Node Package Manager) использует этот `package.json` для управления всеми зависимостями модулей / пакетов для вашего приложения node.js. он установит все зависимости в каталог `./node_modules`.
3. Файл `package.json` обычно находится в корневом каталоге вашего проекта node.js.

```javascript
{
  "name": "myApp",
  "version": "1.0.0",
  "description": "This is my first node.js app.",
  "main": "app.js",
  "homepage": "https://www.fullstacktutorials.com"
  "author": "Full Stack Tutorials",
  "license": "ISC",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "node app.js",
  },
  "dependencies": {
    "body-parser": "^1.18.2",
    "debug": "^3.1.0",
    "express": "^4.16.2",
    "mongoose": "^5.0.4",
    "mysql": "^2.15.0",
    "nodemon": "^1.17.2",
    "request": "^2.83.0"
  },
  "devDependencies": {},
  "repository": {}
}
```
Ниже приведены некоторые важные атрибуты package.json.
1. `name` - название проекта
2. `version` - версия пакета
3. `author` - автор пакета
4. `dependencies` - список зависимостей. npm автоматически устанавливает все зависимости, упомянутые здесь, в папке `node_module` пакета.

---

## 10. Разница между `package.json` и `package-lock.json`?
`package.json`: package.json используется не только для зависимостей - например, для определения свойств проекта, описания, информации об авторе и лицензии и т. д.

`package-lock.json`: package-lock.json в основном используется для блокировки зависимостей с определенным номером версии.

Если `package-lock.json` существует, он отменяет `package.json`

---

## 11. Как удалить зависимость с помощью npm?

```
 npm uninstall dependency-name
 ```

 ---

## 12. Как обновить зависимость с помощью npm?

```
npm update [-g] [<pkg>...]

npm update
```
## 13. В чем разница между тильдой (`~`) и кареткой (`^`) в файле npm `package.json`?

`~` версия 'Приблизительно эквивалентна версии' См. semver

`^` версия 'Совместимо с версией' 

**Зависимости Тильды:**
Если `package.json` вашего приложения содержит:
```js
"dependencies": {
  "module_name": "~1.0.2"
}
```
это означает установить версию 1.0.2 или последнюю версию патча, такую как 1.0.4

**Зависимости каретки:**
Если `package.json` вашего приложения содержит:
```js
"dependencies": {
  "module_name": "^1.0.2"
}
```
Если вы видите ^ 1.0.2, это значит установить версию 1.0.2 или последнюю минорную версию или версию патча, такую как 1.1.0

Более подробно здесь - https://docs.npmjs.com/misc/semver
`~version` "Приблизительно эквивалентна версии"
`^version` "Совместимо с версией" 
`version` должна точно соответствовать версии
`>version` должна быть больше версии
`>=version` т.д.

---
---
# Node.Js Интервью Вопросы | Продвинутый

