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
