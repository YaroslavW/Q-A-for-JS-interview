# Express.JS Интервью Вопросы | 10 лучших вопросов и ответов

![logo-node.js-blitz](img/express-bliz-50.jpg)

## 1. Что такое Express.js ?

- Express js - это бесплатная легковесная инфраструктура веб-приложений на основе js для узлов.
- Он предназначен для создания (одностраничных, многостраничных и гибридных) веб-приложений и API.
- Он был разработан TJ Holowaychuk в 2010 году и написан на JavaScript.

**Особенности Express.js**:
Ниже приведены некоторые основные функции Express Framework:

1. **Middlewares** - Промежуточное программное обеспечение: Установите промежуточное программное обеспечение для ответа на запросы HTTP / RESTful.
2. **Routing** - Маршрутизация: можно определить таблицу маршрутизации для выполнения различных операций HTTP.
3. **Templates** - Шаблоны: динамически отображает HTML-страницы на основе передачи аргументов шаблонам.
4. **High Performance** - Высокая производительность: экспресс подготовить тонким слоем, поэтому производительность адекватна.
5. **Database Support** - Поддержка баз данных: Express поддерживает RDBMS, а также базы данных NoSQL.
6. **MVC Support** - Поддержка MVC: организуйте веб-приложение в архитектуру MVC. Модель-Представление-Контроллер (MVC, Model-View-Controller)
7. Управляет всем, от маршрутов до представления рендеринга и предварительного HTTP-запроса.

---

## 2. Как мы можем разрешить CORS в Express JS? Объясните с примером?

Чтобы разрешить CORS в Express.js, добавьте следующий код в app.js:

```javascript
app.all("*", function(req, res, next) {
  res.set("Access-Control-Allow-Origin", "*");
  res.set("Access-Control-Allow-Methods", "GET, POST, DELETE, PUT");
  res.set("Access-Control-Allow-Headers", "X-Requested-With, Content-Type");
  if ("OPTIONS" == req.method) return res.send(200);
  next();
});
```

---

## 3. Что такое Scaffolding ('строительные леса') в Express JS?

Scaffolding создаёт каркасную структуру приложения

Есть 2 способа сделать это:

1. Express application generator - Экспресс генератор приложений
2. Yeoman

---

**1. Express application generator:**
Используйте экспресс-генератор, чтобы быстро создать каркас приложения.

```
npm install express-generator -g
express myTestExpressApp
```

Эта команда создаст ваш проект с именем - `myTestExpressApp` с указанием файлов / папок в проекте.

1. **bin**: В папке `bin` есть один файл с именем `www`, который является основным файлом конфигурации нашего приложения.
2. **public**: Общая папка содержит JavaScript, CSS, изображения и т. Д.
3. **routes**: папка маршрутов содержит файлы маршрутизации.
4. **views**:Папка вид содержит файлы представления приложения.
5. **app.js**:Файл `app.js` является основным файлом приложения.
6. **package.json**:Файл `package.json` является файлом манифеста. Он содержит все метаданные проекта, такие как пакеты, используемые в приложении (так называемые зависимости) и т. д.

Установите все зависимости, указанные в файле `package.json`:

```
cd myTestExpressApp
npm install
```

## Как включить отладку в экспресс-приложении?

В разных операционных системах у нас есть следующие команды:

### Linux:

```
DEBUG=express:*
node app.js
```

### Windows:

```
set DEBUG=express:*
node app.js
```

---

## 5. Как происходит обслуживание статических файлов в Express?

```javascript
#Example:
app.use(express.static('public'))
app.use('/static', express.static(path.join(__dirname, 'public')))
```

---

## 6. Что такое маршрутизация и как она работает в Express.js?

> Маршрутизация относится к определению того, как приложение отвечает на запрос клиента к конкретной конечной точке, которая представляет собой URI (или путь) и конкретный метод HTTP-запроса (GET, POST и т. д.).

Каждый маршрут может иметь одну или несколько функций-обработчиков, которые выполняются при сопоставлении маршрута.

### Синтаксис роута

```
app.METHOD(PATH, HANDLER)
```

- app - Приложение является экземпляром Express
- METHOD - метод HTTP-запроса в нижнем регистре
- PATH - путь на сервере.
- HANDLER - обработчик (функциция), выполняемой при сопоставлении маршрута.

**Пример**

```js
app.get("/", function(req, res) {
  res.send("Express Js Interview Questions");
});
```

### Динамическая маршрутизация и как это работает в Express.js?

Когда кто-то передает параметры в URL, то есть параметризованном URL, это явление маршрутизации называется динамической маршрутизацией.

```js
var express = require("express"),
  app = express();

app.get("/article/:id", function(req, res) {
  res.render("article" + req.params.id);
});
```

В приведенном выше примере: `id` это параметры, которые могут быть разными для разных вызовов.

---

## 7. Что такое промежуточное ПО в Express Js?

> «Функция, которая вызывается уровнем маршрутизации Express до окончательного обработчика запроса».

Функции промежуточного программного обеспечения могут выполнять следующие задачи:

1. Выполнить любой код.
2. Вносить изменения в объект запроса и ответа.
3. Завершить цикл запрос-ответ.
4. Вызвать следующую функцию промежуточного программного обеспечения в стеке.

_Если текущая функция промежуточного программного обеспечения не завершает цикл запрос-ответ, она должна вызвать next (), чтобы передать управление следующей функции промежуточного программного обеспечения. В противном случае запрос останется висеть._

Приложение Express может использовать следующие типы промежуточного программного обеспечения:

1. Application-level middleware
2. Router-level middleware
3. Error-handling middleware
4. Built-in middleware
5. Third-party middleware

### 1. Промежуточное программное обеспечение уровня приложения - Application-level middleware:

Этот метод промежуточного программного обеспечения привязывается к объекту приложения с помощью метода `app.use ()`.

```js
//This middleware will execute for each route.
app.use(function(req, res, next) {
  console.log("Current Time:", Date.now());
  next();
});
```

### Промежуточное программное обеспечение уровня маршрутизатора - Router-level middleware:

Промежуточное программное обеспечение уровня маршрутизатора работает так же, как промежуточное программное обеспечение уровня приложения, за исключением того, что оно связано с экземпляром `express.Router ()`

### Встроенное промежуточное ПО - Built-in middleware:

Начиная с версии 4.x, Express больше не зависит от Connect.

Express имеет следующие встроенные функции промежуточного программного обеспечения:

- **express.static** обслуживает статические ресурсы, такие как файлы HTML, изображения и т. д.
- **express.json** анализирует входящие запросы с полезными данными JSON. ПРИМЕЧАНИЕ: доступно с Express 4.16.0+
- `express.urlencoded` анализирует входящие запросы с полезными нагрузками в кодировке URL. ПРИМЕЧАНИЕ: доступно с Express 4.16.0+

### Стороннее промежуточное ПО - Third-party middleware:

Существует ряд сторонних промежуточных программ, таких как `body-parser` `cookie-parser`, `mongoose` и так далее.

Для обработки HTTP-запроса POST в Express.js версии 4 и выше вам необходимо установить модуль промежуточного программного обеспечения, называемый `body-parser`, `body-parser` извлекает всю часть тела входящего потока запросов и предоставляет его в `req.body`. Промежуточное программное обеспечение было раньше частью Express.js, но теперь вы должны установить его отдельно.

Они могут быть установлены с помощью команды:

```
>> npm install MODULE_NAME
```

И они могут быть загружены с использованием `require` и использоваться позже.

**Пример:**

```js
var bodyParser = require("body-parser");
app.use(bodyParser.json());
app.use(bodyParser.urlencoded({ extended: false }));
```

---

## 8. Интеграция базы данных в Express Js?
Добавление возможности подключения баз данных к приложениям Express - это всего лишь вопрос загрузки соответствующего драйвера Node.js для базы данных в вашем приложении.

Express JS поддерживает множество СУБД и баз данных NoSQL, таких как

* MongoDB
* MySQL
* Oracle
* PostgreSQL
* SQL Server
* SQLite

**Пример: установки MongoDB**
```js
>>npm install mongodb

var MongoClient = require('mongodb').MongoClient

MongoClient.connect('mongodb://localhost:27017/test_db', function (err, db) {
  if (err) throw err

  db.collection('mammals').find().toArray(function (err, result) {
    if (err) throw err

    console.log(result)
  })
})
```

---

## 9. Обработка ошибок в Express Js и Как перенаправить ошибки 404 на страницу в Express Js?

```js
var express = require('express'),
app = express();

app.use(function (err, req, res, next) {
  console.error(err.stack)
  res.status(500).send('Something went wrong, Express Js Interview Questions')
})
```

```js
//To redirect 404 errors
var express = require('express'),
app = express();

app.use(function(req, res, next) {
    res.status(404).json({
		errorCode: 404, 
		errorMsg: "route not found"
	});
});
```

---

## 10. Как реализовать аутентификацию JWT в приложении Express? Объясните с примером?

* Создайте папку с именем «`keys`» внутри папки проекта.
* Установите некоторые зависимости следующим образом: `npm install jsonwebtoken –-save`
* Добавьте логин маршрутизатора `routes/index.js`

```javascript
router.post('/login, function(req, res) {
  // find the user
  User.findOne({
    name: req.body.username
  }, function(err, res) {
    if (err) throw err;
    if (!res) {
      res.json({ success: false, message: Login failed.' });
    } else if (res) {

      // check if password matches
      if (res.password != req.body.password) {
        res.json({ success: false, message: Login  failed. Wrong password.' });
      } else {
        var token = jwt.sign(res, app.get('superSecret'), {
          expiresInMinutes: 1600 
        });
        // return the information including token as JSON
        res.json({
          success: true,
          message: 'Valid token!',
          token: token
        });
      }   
   }  });
});
```

* Используйте токен в приложении

```javascript
jwt = require("express-jwt");
app.use(function(req, res, next) {
  var token = req.body.token || req.query.token || req.headers['x-access-token'];
  if (token) {
    jwt.verify(token, app.get('superSecret'), function(err, decoded) {      
      if (err) {
        return res.json({ success: false, message: 'Invalid token.' });    
      } else {
        req.decoded = decoded;    
        next();
      }
    });
  } else {
    return res.status(403).send({ 
        success: false, 
        message: 'No token given.' 
    });    
  }
});
```

---
---