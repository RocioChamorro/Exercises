JS / Several solved exercises
​
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
