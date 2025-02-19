# Objects

## There are two ways to create an object in JavaScript

- Object literals
- Constructor functions

- Object literal

```js
let name={
   key1:value1,
   key2:value2
}
```

E.g

```js
newItem ={
   type: 'floral',
   name: dataObject.itemname,
   flowers:{}
   logItem: function (){
      console.log('%c' + this.name, 'font-weight:bold')//making logs bold
   }
}
```

Note: this is the recommended way.

- Constructor Functions OR object-oriented

```js
var object = new Object();
```

```js
function Arrangement(name,vase,quantity=1){
    this.type='floral',
    this.name=name,
    this.flowers ={
        addStem: function(name,color ='Default'){
            this[name] = new Flower(quantity)
        }
    }
    this.logItem: function (){
      console.log('%c' + this.name, 'font-weight:bold')//making logs bold
   }
}

newItem =new Arrangement(dataObject.name, dataObject.vase)
```

## Accessing Objects Properties

To access objects properties,there are two ways:

- Dot Notation:-

```js
object.property
```

- Using bracket Notation

```js
object['property']
```

```js
let person ={
    name:"Collins";
    age:21
};

//Dot Notation
person.name="Kosgei";

//Bracket Notation
let selection ="name";
person[selection] ="Kosgei";
```

## preventing modification of an object property

You can prevent modification of an object property by using Object.defineProperty to set the property as non-writable, non-configurable, and non-enumerable. You can also use Object.freeze to freeze the entire object.

## use of the delete operator

The delete operator removes a property from an object.

## difference between a deep copy and a shallow copy

- Deep copy: A copy of an object and all objects it references, recursively.
- Shallow copy: A copy of an object that only copies the reference addresses of nested objects.

## Objects methods

- Object.create(): Used to create a new object and link it to prototype of existing object.It returns the new object with specified prototye object and properties.

```js
let Student={
    name:"Collins",
    age:21,
    show(){
        console.log("name is "+ this.name "and age is "+ this.age)
    }
}

let std1 = Object.create(Student);//Object creation
std1.name="KipCollo";//same properties
std1.age=3;
std1.display()
```

- Object.keys() and Object.values(): It creates an array cntaining keys of an object and array containing values of an object respectfully.

```js
let Employee={
    Location: "location",
    age:24,
    role:"Frontend"
}

console.log(Object.keys(Employee))//['Location','age','role']
console.log(Object.keys(Employee))//['location',24,'Frontend']
```

- Object.entries() and Object.fromEntries(): creates a nested array of key/value pairs of an object and takes array of key/value pairs and convert them to single object.(Reverse of Object.entries)

```js
let Employee={
    Location: "location",
    age:24,
    role:"Frontend"
}

let EmployeeArray=[{"Location","location"},{"age",24},{"role","Frontend"}]

Object.entries(Employee)//[["Location","location"],["age",24],]"role","Frontend"}]
Object.fromEntries(EmployeeArray)//{ Location: "location",age:24,role:"Frontend"}
```

- Object.seal() and Object.freeze(): The Object.freeze() method freezes an object, preventing new properties from being added to it, existing properties from being removed, and existing properties from being changed,Prevents any changes to an object.Object.seal(): Prevents new properties from being added to an object but allows modification of existing properties.

```js
const frozen = Object.freeze({name:"Collins"});
const sealed = Object.seal({name:"Collins"});

//New property
frozen.name="KipCollo";//frozen = {name:"Collins"}
frozen.name="KipCollo";//sealed = {name:"Collins"}

//Removing existing one
delete frozen.name;//frozen = {name:"Collins"}
delete sealed.name;//sealed = {name:"Collins"}

//update existing one
frozen.name="KipCollo";//frozen = {name:"Collins"}
frozen.name="KipCollo";//sealed = {name:"KipCollo"}

```

- Object.assign(): copies all enumerable own properties from one or more source objects to a target object.
