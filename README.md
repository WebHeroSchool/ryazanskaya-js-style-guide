# JavaScript Style Guide

## Соглашение об именовании

1. Избегайте названий из одной буквы. Имя должно быть наглядным.

👎 **плохо**
``` js
const l = 5;
```
👍 **хорошо**
``` js
const length = 5;
```
2. Используйте camelCase для именования объектов, функций и переменных.

👎 **плохо**
``` js
const my_object = {};

function createNEW_user() {}
```
👍 **хорошо**
``` js
const myObject = {};

function createNewUser() {}
```
3. Используйте PascalCase только для именования конструкторов и классов.

👎 **плохо**
``` js
function user(options) {
  this.name = options.name;
}

const bad = new user({
  name: 'Max',
});
```
👍 **хорошо**
``` js
class User {
  constructor(options) {
    this.name = options.name;
  }
}

const good = new User({
  name: 'Max',
});
```
4. Не используйте `_` в начале или в конце названий. Первый символ не должен быть цифрой.

👎 **плохо**
``` js
__firstName__ = 'Sam';
firstName_ = 'Max';
_firstName = 'James';
1name = 'Michael';
```
👍 **хорошо**
``` js
firstName = 'Sam';
```

## Объявление перменных

1. Используйте `const` для объявления переменных, избегайте `var`. 
Если вам необходимо переопределять значения, то используйте `let`.

👎 **плохо**
``` js
var a = 1;

var count = 1;
if (true) {
  count += 1;
}
```
👍 **хорошо**
``` js
const a = 1;

let count = 1;
if (true) {
  count += 1;
}
```
2. Используйте объявление `const` или `let` для каждой переменной или присвоения.

👎 **плохо**
``` js
const items = getItems(),
    isAnimal = true,
    animal = 'cat';
```
👍 **хорошо**
``` js
const items = getItems();
const isAnimal = true;
const animal = 'cat';
```

## Операторы сравнения и равенства

1. Используйте `===` и `!==` вместо `==` и `!=`.

👎 **плохо**
``` js
a == b
isAnimal == true
animal != 'ball'
0 != '0'
```
👍 **хорошо**
``` js
a === b
isAnimal === true
animal !== 'ball'
0 !== '0'
```
2. Избегайте ненужных тернарных операторов.

👎 **плохо**
``` js
const foo = a ? a : b;
const bar = c ? true : false;
const baz = c ? false : true;
```
👍 **хорошо**
``` js
const foo = a || b;
const bar = !!c;
const baz = !c;
```

## Строки

1. Используйте одинарные кавычки `''` для строк, если это не шаблонная строка. Для шаблонных строк используйте ` `` `

👎 **плохо**
``` js
const name = "James";
const animal = `cat`
```
👍 **хорошо**
``` js
const name = 'James';
const animal = `cat ${name}`
```
2. При создании строки программным путём используйте шаблонные строки вместо конкатенации. 

👎 **плохо**
``` js
function sayHi(name) {
  return 'Hello, ' + name + '!';
}
```
👍 **хорошо**
``` js
function sayHi(name) {
  return `Hello, ${name}!`;
}
```

## Объекты

1. Для создания объекта используйте литеральную нотацию.

👎 **плохо**
``` js
const item = new Object();
```
👍 **хорошо**
``` js
const item = {};
```
2. Используйте сокращённую запись свойств объекта.

👎 **плохо**
``` js
const lukeSkywalker = 'Luke Skywalker';

const obj = {
  lukeSkywalker: lukeSkywalker,
};
```
👍 **хорошо**
``` js
const lukeSkywalker = 'Luke Skywalker';

const obj = {
  lukeSkywalker,
};
```

## Массивы

1. Для создания массива используйте литеральную нотацию.

👎 **плохо**
``` js
const items = new Array();
```
👍 **хорошо**
``` js
const items = [];
```
