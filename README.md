# learning-oop-and-oloo-js

## add methods on the global Object so every new obj(regardless of how you create it) will have it by default
```javascript
// Place method inside the global Object so every new object will have that method by default

Object.prototype.greet = function(){
  console.log("hello "+this.x)
}

var obj1 = {
  x: "John"
}

var obj2 = new Object();
obj2.x = "Jane";

obj1.greet(); // hello John
obj2.greet(); // hello Jane
```

## create a "proto" object and use it to store all methods for other objects
```javascript
// create a "proto" object whith the sole purpose of providing methods to other different objectss

var proto = {
  greet: () => console.log('hello world')
}

var obj1 = Object.create(proto);

obj1.greet(); // hello world

/////
/////  "proto" with ES6 classes
/////

class Proto {
  greet(){ 
    console.log('hello world!')
  }
}

class Obj2 extends Proto{
  // your code here
}

var obj2 = new Obj2();
obj2.greet(); // hello world!
```
