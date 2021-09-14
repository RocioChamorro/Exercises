# JS / Several solved exercises
1. Crear una función que reciba un objeto y un string…
El string va a ser el nombre de una propiedad, y 
esa función tiene que validar si existe esa propiedad dentro del objeto que le mandes
la función debe retornar true o false
  ```js
  var Car = {
    wheels: 4,
    company: 'honda',
    name: 'civic',
    year: 2016
}

function validate(obj, string) {
    var array = Object.keys(obj)
    for (let i = 0; i < array.length; i++) {
        if(array[i] == string) return true;
    }
    return false;
}

console.log(validate(Car, 'name'))
  ```
2. Create an object that will be filled only by a function inside of it, 
and not from someone outside of it's function.. example:
 ```js

let myObject = {
    myFunction: function ()... // This function is supposed to fill this object
}
  ```
 myObject.myNewProp = "Hello world" // This should throw an exception or error because we don't want this object to be filled from outside... 
It supposed to be filled using it's own function
Add any type of element on the object.. arrays, objects, int, strings, etc
  ```js
let myObject = {
    myFunction: function (prop, _value){
        Object.defineProperty(this, prop,  {
            value: _value,
            enumerable: true
          })
    }
}

console.log(myObject.myFunction('name','Rocio'));
console.log(myObject);

Object.freeze(myObject); //impide que se le agreguen nuevas propiedades,..etc.

console.log(myObject.myFunction('lastname','Chamorro'));
console.log(myObject); //Cannot define property lastname, object is not extensible
  ```
3. var simpleExercise = [{a: 11, b:224, name: "M48 Bulldog"}, {a:23, b:56, name: "Object 140"}, {a: 32, b:75, name: "T57 Heavy"}];
Hacer una función para que reciba ese arreglo de objetos
y que retorne la suma de "a" y "b" de cada objeto y concatenarlo 
al String "name" para que devuelva algo así:
["235 M48 Bulldog-=-79 Object 140-=-107 T57 Heavy" ]
  ```js
  const simpleExercise = [{a: 11, b:224, name: "M48 Bulldog"}, {a:23, b:56, name: "Object 140"}, {a: 32, b:75, name: "T57 Heavy"}];

function concatObjectproperties(array) {
    let text= "";
    for (let i = 0; i < array.length; i++) {
        let partialText = `${array[i].a + array[i].b} ${array[i].name}`;
        text = text != "" ? text.concat('-=-', partialText) : partialText;
    }
    return text;
}

console.log(concatObjectproperties(simpleExercise));
  ```
3.  Realizar el Challenge del Capítulo N°1 de You don’t know JS.
  ```js
  function calculateTax(amount) {
    const TAX_RATE = 0.08;
	return amount * TAX_RATE;
}

function formatAmount(amount) {
	return "$" + amount.toFixed( 2 );
}

function validatePurchase(bank_balance) {
    const SPENDING_THRESHOLD = 200;
    const PHONE_PRICE = 99.99;
    const ACCESSORY_PRICE = 9.99;

    var amount = 0;
    // keep buying phones while you still have money
    while (amount < bank_balance) {
        // buy a new phone!
        amount = amount + PHONE_PRICE;

        // can we afford the accessory?
        if (amount < SPENDING_THRESHOLD) {
            amount = amount + ACCESSORY_PRICE;
        }
    }

    // don't forget to pay the government, too
    amount = amount + calculateTax(amount);

    console.log("Your purchase: " + formatAmount(amount));
    // Your purchase: $334.76

    // can you actually afford this purchase?
    if (amount > bank_balance) {
        console.log("You can't afford this purchase. :(");
    }
}

//Bonus Challenge
let bank_balance = prompt("Ingrese el saldo de su cuenta bancaria en $");
validatePurchase(bank_balance);

  ```
4.  Classes were added in last version of JavaScript (called ECMAScript 6 or just ES6). It's something similar to how classes work in other languages (Java, Ruby, etc). This is a 	very important concept in programming, so sooner or later you'll want to learn about it. (And I highly recommend you to do it before the Java modules).


Create a  Car class:

1) Add properties like model, so you can create a "Ford" with model "Mondeo". Add the properties you like in the constructor method.
2) Add a method to accelerate
3) Add a method to stop
4) Add a method turn directions
5) Add a method call status to display the information of the car (properties, methods, etc)

Instance at least 2.
  ```js
function palindrome(string) {
    let account = 0;
    let text = string.replace(/\s+/g, ''); //texto.split(" ").join("");
    text = text.toLowerCase();
    for (let i = text.length - 1; i < text.length; i--) {
        const letter = text[i];
        if (i > text.length / 2) {
            if (text[account]!= letter) return console.log("No es una palabra palíndromoi");
            account++;
        }
        else break;
    }
    return console.log("Es una palabra palíndromo");
}

palindrome('Yo hago yoga hoy');// return "Es una palabra palíndromo"
  ```
  
  5.  Create a Polygon class that has the following properties:
1) A constructor that takes an array of integer values describing the lengths of the polygon's sides.
2) A perimeter() method that returns the polygon's perimeter.
Locked code in the editor tests the Polygon constructor and the perimeter method.

  ```js
/*
 * Implement a Polygon class with the following properties:
 * 1. A constructor that takes an array of integer side lengths.
 * 2. A 'perimeter' method that returns the sum of the Polygon's side lengths.
 */

let Polygon = class {
    constructor(arr) {
        this.arr = arr;
    }
  
    perimeter() {
        var sum = 0;
        for (let i = 0; i < this.arr.length; i++) {
            const element = this.arr[i];
            sum += element
        }
        return sum;
    }
}

const rectangle = new Polygon([10, 20, 10, 20]);
const square = new Polygon([10, 10, 10, 10]);
const pentagon = new Polygon([10, 20, 30, 40, 43]);

console.log(rectangle.perimeter());
console.log(square.perimeter());
console.log(pentagon.perimeter());
  ```
