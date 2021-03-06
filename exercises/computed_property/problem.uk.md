У ES6 було покращено спосіб доступу до літералів об'єктів та їх визначення. Тепер же можна використовувати вирази як імена властивостей. 

Раніше вам доводилось визначити динамічні властивості наступним чином:

```javascript
var prop = "foo";

var obj = {};
obj[prop] = "bar";
```

тепер, в ES6, це можна написати так:

```javascript
var prop = "foo";
var obj = {
  [prop]: "bar"
};
```

Це називається `Обчислені властивості`.

Вміст `[]` може бути також і функцією:

```javascript
var obj = {
  // використання вбудованої функції
  [(()=>"bar" + "baz")()]: "foo"
};
```

У цьому випадку індекс - це рядок, що повертає функція. З новим синтаксисом `Обчислені властивості` ви можете прописувати динамічні властивості без використання тимчасових змінних.

# Вправа

Перепишіть наступний код за допомогою нового методу `Обчислені властивості`:

```javascript
var evenOrOdd = +process.argv[2];
var evenOrOddKey = evenOrOdd % 2 === 0 ? "even" : "odd";
var sum = +process.argv[3] + evenOrOdd;
var obj = {};
obj[evenOrOddKey] = evenOrOdd;
obj[sum] = sum;
console.log(obj);
```

Спробуйте вирішити це без жодної тимчасової змінної.
