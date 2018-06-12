# ES6 New Features

## Let

```javascript
let sound = "Wow!";
function getSound() {
    let sound = "So cool!";
    return sound;
};
console.log(getSound());
```

## Arrow Functions

```javascript
function circleArea1(r) {
    var PI = 3.14;
    return PI * r * r;
};

let circleArea2 = (r) => {
    const PI = 3.14; // new keyword 'const'
    return PI * r * r;
}

// when have one parameter, no need parenthense and body block;
let circleArea3 = r => 3.14 * r * r;

console.log(circleArea1(3));
console.log(circleArea2(3));
console.log(circleArea3(3));
```

## Template Literals

```javascript
let myName = "Ocean";

console.log("My name is " + myName);
console.log(`My name is ${myName}`);
// making a newline
console.log(`My name is 
${myName}`);

let a = 9;
let b = 8;
console.log("Output: ${a+b}");
```

## Spread Operator

```javascript
// ex1
function addNumbers(a, b, c) {
    console.log(a + b + c);
};

var nums = [3, 5, 7];
addNumbers(nums[0], nums[1], nums[2]);
addNumbers(...nums);


// ex2
var meats = ['bacon', 'ham'];
// adding meats to food
var food = ['apples', ...meats, 'kiwi', 'rice'];
console.log(food);
```
## Classes

```javascript
class Person {
    
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }
    
    displayName() {
        console.log(this.name);
    }
}

let ocean = new Person('Ocean', 22);
let oceanNguyen = new Person('Ocean Nguyen', 24);

console.log(ocean.displayName());
console.log(oceanNguyen.displayName());
```
## Inheritance

```javascript
class Programmer extends Person {
    
     constructor(name, age, language) {
        super(name, age);
        this.language = language;
    }
}

let ocean = new Person('Ocean', 22, 'JavaScript');
console.log(ocean.displayName());
```
## Generators

```javascript
function* getNextId() {
    let id = 0;
    while(id < 3) {
        yield id++;
    }
}

let createUser = getNextId();
console.log(createUser.next().value);
console.log(createUser.next().value);
console.log('writing something!');
console.log(createUser.next().value);
console.log(createUser.next().value);
```
