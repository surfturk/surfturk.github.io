---
layout: post
title:      "Javascript Object Orientation"
date:       2020-10-02 14:07:01 -0400
permalink:  javascript_object_orientation
---


Ahhh Javascript! So JS is an object orientated programming language and that means almost everything in JS can be an object. We mearly use the the Object() syntax to create an object. This is known as an object constructor. For example, if I write let cat = new Object() this will create a new object called cat that does not contain any data. I can then associate data with this syntax, cat.name = "Jimi". I could then console.log that object like so, console.log(cat) and it would return Object {name: "Jimi"}. We have associated a key and value with the new object. 

# JS prototyping

Now, a new object inherits from a constructor object and a contructor object inherits propeties and methods from Object.prototype. This is know as the prototype chain. For example, lets say I create a cat constructor function: 

function Cat(name, species, age) {
  this.name = name;
  this.species = species;
  this.age = age;
}

Then I assign let cat1 = new Cat('Jimi', 'calico', 5) and I type cat1 in the console.  I'll get a bunch of data back about the object. 

age: 5
name: "Jimi"
species: "calico"
__proto__: Object

We obviously see the key and values we assigned to the object but we also see proto object as well. If I click on proto object:

constructor: ƒ Cat(name, species, age)
__proto__: Object

This shows the constructor we created in our function cat inherited but we also see proto object again. When I click on that I get:

constructor: ƒ Object()
hasOwnProperty: ƒ hasOwnProperty()
isPrototypeOf: ƒ isPrototypeOf()
propertyIsEnumerable: ƒ propertyIsEnumerable()
toLocaleString: ƒ toLocaleString()
toString: ƒ toString()
valueOf: ƒ valueOf()
__defineGetter__: ƒ __defineGetter__()
__defineSetter__: ƒ __defineSetter__()
__lookupGetter__: ƒ __lookupGetter__()
__lookupSetter__: ƒ __lookupSetter__()
get __proto__: ƒ __proto__()
set __proto__: ƒ __proto__()
﻿
 
 
​
Woah, Thats a lot. So these are methods that we inherit from the main prototype object. So, the chain looks like this:
cat1 = Cat = Object. The cat1 instance inherits from the Cat prototype object, and the Cat protoype object inherits from the Object prototype. This is the protoype chain.  Why is this so poweful? Well, lets say we want to add a method to the Cat function that alerts the user with the data in their new object. We could write this: 



Cat.prototype.hello= function() {
  alert(this.name + " is a " + this.species + " and is  " + this.age + " years old") }

Then we could call the function on an object we already created:

cat1.hello()

and that prompts an alert box says jimi is a calico and is 5 years old. We could also create a new object and use the new function as well.

let cat2 = new Cat("Winry","faded calico", 4)
cat2.hello()

and we get another alert saying Winry is a faded calico and is 4 years old.

This is awesome because we are ablew to add methods at the prototype object level and every instance of that object will automatically inherit that method. Pretty powerful.



# JS static method
The static keyword is a keyword that is used to denote a method or object at the class level. These are not called on instances of the class but rather at the class level. For example, let say I create a class Cat like so:

class Cat {
    constructor(name, species, age) {
      this.name= name;
      this.species = species;
      this.age = age;
      Cat.all.push(this);}

		
static all = [] }
		
So what is going on here? Well, I've created a cat class with a constructor function that take in those keys and values.    I'm also pushing an an instance of the class upon creation into the Cat all array. If we look down below we can see an      empty array that is static. This means that this array is at the class level and It is global, thus I can use it anywhere in my application. we could have an app that renders a cat in html and we could have a class method like so:


```
class Cat {
    constructor(name, species, age) {
      this.name= name;
      this.species = species;
      this.age = age;
      Cat.all.push(this);}

		
static all = [] 

static header() {
   return <h1>All Cats</h1>
}


renderCat() {
       return(
         `
         <ul>
         <li>Cat name ${this.name}</li>
          <li> Cat Species  ${this.species}</li>
          <li> Cat Age ${this.age}</li>
         </ul>) } }
	```
	
	
	

So if we look at the static method header, We see that it will return an h1 that says all cats. This is a static method so  we would not be able to say type cat1.header or cat2.header. These are instances of the Cat class. 
We would instead  type Cat.header and it would return the h1 all cats. This highlights the difference between instance methods and static  methods.
 
 
 
