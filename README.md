# addressbookJavascript
```
var bob = {
    firstName: "Bob",
    lastName: "Jones",
    phoneNumber: "(650) 777-7777",
    email: "bob.jones@example.com"
};

var mary = {
    firstName: "Mary",
    lastName: "Johnson",
    phoneNumber: "(650) 888-8888",
    email: "mary.johnson@example.com"
};

var contacts = [bob, mary];

function printPerson(person) {
    console.log(person.firstName + " " + person.lastName);
}

function list() {
	var contactsLength = contacts.length;
	for (var i = 0; i < contactsLength; i++) {
		printPerson(contacts[i]);
	}
}


//search("Jones");

 function add(firstName,lastName, email, phoneNumber){
    var con = {
           firstName: firstName,
           lastName: lastName,
           phoneNumber: phoneNumber,
           email: email
            };
    return con;
    }
contacts[contacts.length]=add("john", "sow", "john@gmail.com","(650) 888-8888" );
list();
```


```
console.log( bob.hasOwnProperty('bob') ); // should print true
console.log( bob.hasOwnProperty('kate') ); // should print false
```
```
console.log( typeof bob ); 
```
# loop
```
var nyc = {
    fullName: "New York City",
    mayor: "Bill de Blasio",
    population: 8000000,
    boroughs: 5
};

// write a for-in loop to print the value of nyc's properties
for (var property in nyc){
    console.log(nyc[property]);
    }
```
# class
```
function Person(name,age) {
  this.name = name;
  this.age = age;
}

// Let's make bob again, using our constructor
var bob = new Person("Bob Smith", 30);
var susan = new Person("Susan Jordan", 35);

// make your own class here
function Circle(radius) {
  this.radius = radius;
}
```
# class 2
```
function Dog (breed) {
  this.breed = breed;
}

// here we make buddy and teach him how to bark
var buddy = new Dog("Golden Retriever");
buddy.bark = function() {
  console.log("Woof");
};
buddy.bark();

// here we make snoopy
var snoopy = new Dog("Beagle");
// we need you to teach snoopy how to bark here
snoopy.bark = function() {
  console.log("Woof");
};

snoopy.bark();
```
# class 3
```
function Person(name,age) {
  this.name = name;
  this.age = age;
}
// a function that prints the name of any given person
var printPersonName = function (p) {
  console.log(p.name);
};

var bob = new Person("Bob Smith", 30);
printPersonName(bob);

// make a person called me with your name and age
var me = new Person("ebenezer", 28);
// then use printPersonName to print your name
printPersonName(me);
```
# class 4
## Automatically teaching all dogs to bark
```
function Dog (breed) {
  this.breed = breed;
};

// here we make buddy and teach him how to bark
var buddy = new Dog("golden Retriever");
Dog.prototype.bark = function() {
  console.log("Woof");
};
buddy.bark();

// here we make snoopy
var snoopy = new Dog("Beagle");
/// this time it works!
snoopy.bark();
```
# class 5
```
function Cat(name, breed) {
    this.name = name;
    this.breed = breed;
}

// let's make some cats!
var cheshire = new Cat("Cheshire Cat", "British Shorthair");
var gary = new Cat("Gary", "Domestic Shorthair");

// add a method "meow" to the Cat class that will allow
// all cats to print "Meow!" to the console
Cat.prototype.meow = function(){
    console.log("Meow!");
    }

// add code here to make the cats meow!
cheshire.meow();
gary.meow();
```
# class 6
```
// create your Animal class here
function Animal(name, numLegs){
    this.name = name;
    this.numLegs = numLegs;
}

// create the sayName method for Animal
Animal.prototype.sayName = function(){
    console.log("Hi my name is " + this.name);
    }


// provided code to test above constructor and method
var penguin = new Animal("Captain Cook", 2);
penguin.sayName();
```
# inheritance
```
// the original Animal class and sayName method
function Animal(name, numLegs) {
    this.name = name;
    this.numLegs = numLegs;
}
Animal.prototype.sayName = function() {
    console.log("Hi my name is " + this.name);
};

// define a Penguin class
function Penguin(name){
    this.name = name;
    this.numLegs = 2;}

// set its prototype to be a new instance of Animal. The Penguin class inherits the properties and methods of Animal
Penguin.prototype = new Animal();

var penguin = new Penguin("water penguin");
penguin.sayName()

```
# inheritance 1
```
function Penguin(name) {
    this.name = name;
    this.numLegs = 2;
}

// create your Emperor class here and make it inherit from Penguin
function Emperor(name){
    this.name = name;
    }
Emperor.prototype = new Penguin();
// create an "emperor" object and print the number of legs it has
var emperor = new Emperor("small emperor");
console.log(emperor.numLegs);
```
# inheritance 2
```
// original classes
function Animal(name, numLegs) {
    this.name = name;
    this.numLegs = numLegs;
    this.isAlive = true;
}
function Penguin(name) {
    this.name = name;
    this.numLegs = 2;
}
function Emperor(name) {
    this.name = name;
    this.saying = "Waddle waddle";
}

// set up the prototype chain
Penguin.prototype = new Animal();
Emperor.prototype = new Penguin();

var myEmperor = new Emperor("Jules");

console.log( myEmperor.saying ); // should print "Waddle waddle"
console.log( myEmperor.numLegs ); // should print 2
console.log( myEmperor.isAlive ); // should print true
```
# inheritance 3: Public and private variables
```
function Person(first,last,age) {
   this.firstname = first; // this is a public variable
   this.lastname = last;
   this.age = age;
   var bankBalance = 7500; // this is a private variable
  
   this.getBalance = function() {
      // your code should return the bankBalance
      return bankBalance;
   };
}

var john = new Person('John','Smith',30);
console.log(john.bankBalance); // note, this fails because bankBalance is set to private

// create a new variable myBalance that calls getBalance()
var myBalance = john.getBalance(); // only way to access private variables
console.log(myBalance);
```
# creating and calling private methods
```
function Person(first,last,age) {
   this.firstname = first;
   this.lastname = last;
   this.age = age;
   var bankBalance = 7500;
  
   var returnBalance = function() {
      return bankBalance;
   };
       
   // create the new function here
   this.askTeller = function(){
       return returnBalance
       };
}

var john = new Person('John','Smith',30);

var myBalanceMethod = john.askTeller();
var myBalance = myBalanceMethod();
console.log(myBalance);

```
# pass value to private methods
```
function Person(first,last,age) {
   this.firstname = first;
   this.lastname = last;
   this.age = age;
   var bankBalance = 7500;
  
   this.askTeller = function(pass) {
     if (pass == 1234) return bankBalance;
     else return "Wrong password.";
   };
}

var john = new Person('John','Smith',30);
/* the variable myBalance should access askTeller()
   with a password as an argument  */
var myBalance = john.askTeller(1234);
```
# review
```
var languages = {
    english: "Hello!",
    french: "Bonjour!",
    notALanguage: 4,
    spanish: "Hola!"
};

// print hello in the 3 different languages
for(var lang in languages){
    if((typeof languages[lang]) === "string"){
        console.log(languages[lang]);
        }
}
```
# review 1
```
function Dog (breed) {
    this.breed = breed;
};

// add the sayHello method to the Dog class 
// so all dogs now can say hello
Dog .prototype.sayHello = function()
   {
       console.log("Hello this is a "+ this.breed +" dog");
    }

var yourDog = new Dog("golden retriever");
yourDog.sayHello();

var myDog = new Dog("dachshund");
myDog.sayHello();

```
# review 2 : make all properties private and expose only the method
```
function StudentReport() {
    var grade1 = 4;
    var grade2 = 2;
    var grade3 = 1;
    this.getGPA = function() {
        return (grade1 + grade2 + grade3) / 3;
    };
}

var myStudentReport = new StudentReport();

for(var x in myStudentReport) {
    if(typeof myStudentReport[x] !== "function") {
        console.log("Muahaha! " + myStudentReport[x]);
    }
}

console.log("Your overall GPA is " + myStudentReport.getGPA());
```
