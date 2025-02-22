# Callback Function чист?

_Callback function_ – ин як функсия аст, ки ҳамчун аргумент ба функсияи дигар дода мешавад ва баъдтар иҷро мегардад.

 Чаро callback лозим аст?

- Барои иҷрои асинхронӣ (масалан, дархост ба сервер, таймерҳо, хондани файл ва ғ.).
- Барои такроркорӣ дар массивҳо (масалан, forEach(), map(), filter() ва ғ.).
- Барои интиқоли код ба функсияи дигар ва иҷрои он вақте ки лозим аст.

## Чӣ тавр callback кор мекунад?

 Ба як функсия дигар функсияро ҳамчун аргумент медиҳем ва онро дохили ҳамон функсия даъват мекунем.

### Мисоли оддӣ:

function greet(name, callback) {
  console.log("Hello, " + name);
  callback(); // Функсияи callback-ро даъват мекунем
}

function sayGoodbye() {
  console.log("Goodbye!");
}

greet("Zainulobiddin", sayGoodbye);

Hello, Zainulobiddin
Goodbye!

###  Фаҳмондашавӣ:

greet(name, callback) функсияест, ки callback-ро қабул мекунад.
Вақте ки greet("Zainulobiddin", sayGoodbye) даъват мешавад:

- console.log("Hello, " + name) → "Hello, Zainulobiddin" менависад.
- callback() → sayGoodbye() даъват шуда, "Goodbye!"-ро чоп мекунад.

### Callback дар методҳои массив

Методҳои forEach(), map(), filter() ва ғ. callback-ро истифода мебаранд.

Мисоли forEach()

let numbers = [1, 2, 3, 4, 5];

numbers.forEach((num) => {
  console.log(num * 2);
});

2
4
6
8
10

###  Фаҳмондашавӣ:

- forEach() ба ҳар як элемент callback-ро мефиристад.
- num \* 2-ро барои ҳар як унсур ҳисоб мекунад.

### Хулоса

_Callback function_ – ин як функсияест, ки ба функсияи дигар дода мешавад ва баъдтар иҷро мешавад.

# Методҳои Callback дар JavaScript

Методҳои _callback_ – ин методҳои массив мебошанд, ки ҳамчун параметр функсияи callback-ро қабул мекунанд ва онро барои ҳар як элементи массив иҷро мекунанд.

Ин методҳо кор бо массивҳоро осон ва хонданишаванда мекунанд. 

## 1. forEach() → Итератсия дар массив

 Ҳангоми иҷрои функсия барои ҳар як элемент, аммо бе баргардонидани массиви нав, истифода мешавад.

#### Мисол:

let numbers = [1, 2, 3, 4, 5];

numbers.forEach((num) => {
  console.log(num * 2);
});

2
4
6
8
10

 forEach() танҳо давр мезанад, аммо чизе барнамегардонад.

## 2. map() → Баргардонидани массиви нав

 Барои тағйири ҳар як элемент ва баргардонидани массиви нав истифода мешавад.

#### Мисол:

let numbers = [1, 2, 3, 4, 5];

let doubled = numbers.map((num) => num * 2);
console.log(doubled);

[2, 4, 6, 8, 10]

## 3. filter() → Баргардонидани массиви филтршуда

 Барои баргардонидани танҳо элементҳое, ки ба шарт ҷавобгӯ ҳастанд, истифода мешавад.

#### Мисол:

let numbers = [10, 15, 20, 25, 30];

let greaterThan20 = numbers.filter((num) => num > 20);
console.log(greaterThan20);

[25, 30]

 filter() элементҳоро нест мекунад, ки ба шарт ҷавобгӯ нестанд.

## 4. find() → Баргардонидани аввалин элементи мувофиқ

 Барои баргардонидани аввалин элементе, ки ба шарт ҷавобгӯ аст, истифода мешавад.

Мисол:

let numbers = [5, 10, 15, 20];

let found = numbers.find((num) => num > 10);
console.log(found);

15

 find() танҳо аввалин элементи мувофиқро бармегардонад.

## 5. some() → Санҷиши вуҷуд доштани ҳадди аққал як элемент

 Агар ҳадди аққал як элемент ба шарт ҷавобгӯ бошад, true бармегардонад.

#### Мисол:

let numbers = [2, 4, 6, 8];

let hasOdd = numbers.some((num) => num % 2 !== 0);
console.log(hasOdd);

false

 some() агар ҳадди аққал як элемент ба шарт ҷавобгӯ бошад, true бармегардонад.

## 6. every() → Санҷиши ҳама элементҳо

 Агар ҳамаи элементҳо ба шарт ҷавобгӯ бошанд, true бармегардонад.

Мисол:

let numbers = [2, 4, 6, 8];

let allEven = numbers.every((num) => num % 2 === 0);
console.log(allEven);

true

## 7. reduce() → Баргардонидани як арзиш

 Барои омезиши ҳама элементҳо ба як арзиш истифода мешавад.

Мисол:

let numbers = [1, 2, 3, 4, 5];

let sum = numbers.reduce((acc, num) => acc + num, 0);
console.log(sum);

15

 reduce() қимматҳоро якҷоя карда, як арзиши ягона месозад.
