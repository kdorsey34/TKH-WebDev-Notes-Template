# Week 6
## October 17th, Monday 

# Topic: Javascript Objects 

___

### Day 1, [10/17]

#### 🗒️Notes from class:

#### 📚Resources:


#### 💭Daily Reflection:

💡3 Things I learned today:
1. Javascript Objects
2. Dot/bracket notation 
3. key:value = property

👁️Two things I would like to know more about:
1. Looping
2.  

✋One thing I'm having trouble understanding:
1. Using objects for lookups-freecodecamp


___

### Day 2, [month]/[day] 

#### 🗒️Notes from class:

#### 📚Resources:


#### 💭Daily Reflection:

💡3 Things I learned today:
1. 
2. 
3. 

👁️Two things I would like to know more about:
1. 
2. 

✋One thing I'm having trouble understanding:
1. 

___

### Day 3, [10/19]
#### 🗒️Notes from class:
*/



//Yesterday we saw the example of a bike as an object
let bike = {
  handlebars: "round bars",
  color: "blue",
  wheels: 4,
};

//So we could represent a real world object - a bike - as an object, as digital data

//Now we have a single bike represented, but what if we wanted to represent multiple bikes? We could repeat ourselves and create mutiple bike objects saved to different variables with different property values
let bike2 = {
  handlebars: "flat bars",
  color: "red",
  wheels: 2
};

let bike3 = {
  handlebars: "mustache bars",
  color: "black",
  wheels: 3,
};

//This is not following the principle of DRY code - Don't Repeat Yourself.

//This is where Classes come in. We can think of Classes as a 'blueprint' or template for an object. Lets look at the syntax for declaring a class

// A JavaScript class is a type of function

//class keyword, class name uppercased
class Bike {
  //constructor function - takes in these params when a new Bike instance is created
  //constructor builds the object with the given data, It is used to initialize object properties
  //It is executed automatically when a new object is created
  constructor(handlebars, color, numOfWheels) {
    //this = referring to itself
    // https://www.w3schools.com/js/js_this.asp

    //this.handlebars is the Bike's handlebars property
    //handlebars(on the right of the =) is a value coming in from the constructor
    this.handlebars = handlebars;
    this.color = color;
    this.numOfWheels = numOfWheels;
  }
}

//create a new instance of Bike saved into the variable wrensBike
let wrensBike = new Bike("flat bars", "purple", 2 )
//console.log(wrensBike)

//Create another instance of Bike

//Do Now: Create a class named Student that takes in name, age, and major as constructor paramaters. create an instance of student saved to a variable and console.log the variable

//Methods
//We can add methods to an object we declare without a class:
let bike4 = {
  handlebars: "mustache bars",
  color: "black",
  wheels: 3,
  ride: function rideBike(){
    return(`weee this is fun`)
  }
};
//console.log(bike4.ride())

//we can also include functions as methods in a class declaration

//Person example
class Person {
  constructor(name){
    this.name = name
  }
  //greet is a method of the Person class
  greet(){
    return `Nice to meet you ${this.name}!`
  }
}
let wren = new Person("Wren")
console.log(wren.greet())

//Car example
//adapted from https://www.w3schools.com/js/js_classes.asp
class Car {
  constructor(make, year) {
    this.make = make;
    this.year = year;
  }
  age() {
    let currentYear = 2022
    return currentYear - this.year;
  }
}

let myCar = new Car("Ford", 2014);
//console.log(`My car is ${myCar.age()} years old`)


//Fruit example
class Fruit {
  constructor(name, color) {
    this.name = name;
    this.color = color;

  }
  //daysOld is a paramater passed when isGoodToEat() method is called
  //pass name as this.name
  isGoodToEat(daysOld, name = this.name) {
    if (daysOld <= 3) {
      return `Yum that ${name} looks good!`;
    } else if (daysOld <= 6) {
      return `Better eat that ${name} quick...`;
    } else {
      return `What is that gross squishy thing... a ${name} ?!?`;
    }
  }
}

let banana = new Fruit("banana", "yellow");
//call isGoodToEat on banana object, passing a number for the daysOld param
//console.log(banana.isGoodToEat(2));

//Do now
//add a method to your student Class that returns a message including the student's name, age, and major
//console.log the result of calling the method



//Parent Classes
//There are time when we want to use a general class, and add more unique properties and/or methods to it

//Parent class is general, child or subclass adds specificity

// https://javascript.info/class-inheritance

class Animal {
  constructor(name) {
    this.speed = 0;
    this.name = name;
  }
  //speed is an argument passed when calling run
  run(speed) {
    //the animal object's speed property is updated using this
    this.speed = speed;
    return `${this.name} runs with speed ${this.speed}.`
  }
  stop() {
    //the animal object's speed property is again updated using this
    this.speed = 0;
    return `${this.name} stands still.`
  }
}

let animal = new Animal("My animal");
let dog = new Animal("dog")
console.log(dog.run(8))
//can still access speed property
console.log(dog.speed)

//calling the run method updates the value of the speed property
console.log(dog.run(10));
console.log(dog.speed);


/*
…And we would like to create another class Rabbit.

As rabbits are animals, Rabbit class should be based on Animal, have access to animal methods, so that rabbits can do what “generic” animals can do.

The syntax to extend another class is: class Child extends Parent.
*/

//create class Rabbit that inherits from Animal:
class Rabbit extends Animal {
    constructor(name, earType){
        //super is getting the name property from Animal
        //must be called first! before anything else in constructor
        //super(name)
        //this.earType = earType
        //constructor functional is optional
    }
    //But in order to append like a name, you have to use a constructor and a super method in the constructor to append the name to the name in the animal class.

  hide() {
  return`${this.name} hides!`
  }
}

let rabbit = new Rabbit("White Rabbit");

//objects made with class Rabbit still have access to methods from class Animal
rabbit.run(5); // White Rabbit runs with speed 5.
rabbit.hide(); // White Rabbit hides!

#### 📚Resources:freecodecamp


#### 💭Daily Reflection:

💡3 Things I learned today:
1. Recursion 
2. Nesting For Loops
3. While Loops

👁️Two things I would like to know more about:
1. All of the above items
2. 

✋One thing I'm having trouble understanding:
1. Recursion-Completely confused by this...lol
 

