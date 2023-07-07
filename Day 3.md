<h1 align="center">🚀 Day 2 </h1>

# course: [JavaScript: From First Steps to Professional](https://frontendmasters.com/courses/javascript-first-steps/)

# 🔎 Topics:
**1. General Notes**

**2. Array**

**3. Objects**

## ✨️ First: General Notes
### 📝 Notes:
#### ⚈ Declaration & Initialization
* To declare variables I use let,var,const keywerds.
* If I declare a variable and I don't initialize it, it will has undefined value.
* When I use const, I must initialize the variable.
* The variable name cannot begin with a number.
* When I declare a variable, the variable will point to the value not contain the value.

#### ⚈ Assignment
```
let variable1="Safa"
let variable2= variable1 //variable2 will point to Safa not to variable1.
variable1="newValue" //this statement has no effect on variable2.
```
#### ⚈ Statments vs Expressions 
1. Expression: when I ask JS what is the value for somrthing, ex: ``` 6*3 ```
2. Statment: when I tell JS to do an action, ex: ``` document.title="New Page" ```

## ✨️ Second: Array
**Array: type of global object that is used to store data.**

### Array method:
Just to use in examples: ``` let arr= [100, 2, 50]; ```
* I can use indexOf() and includes() methods. This method mentioned before
* sort(): will sort the array's element alphabetical, this method treat the elements as string, ex: ```arr.sort(); //this will output [100, 2, 50] ```
* join(): will return string contain the array values, separated by the specified separator, ex: ```arr.join(' & ') //output:'100 & 2 & 50' ```
* push(value): will add the value as the last element in an array ex: ```arr.push(2); ```
* pop(): return the last value in an array and delete it from the array, ex: ``` let lastElement= arr.pop(); //lastElemnt=50 ```
* concat(): will return new array that its elements from joining two arrays together ```let joinArrays= [1,2].concat([3,4]) //joinArrays will be [1, 2, 3,4]

### 📝 Notes:
1. Array could be empty or has single element also in JS can contains a lot of dataType in same array.
2. Some action change the array (aka in Place )like: push() and some not,it is just make copy from it like: concat().
3. When I assign an array to a variable I assign it by refrence that means that every change in the array will change also in the content of the variable.

### Array vs Sttring 
Array=> is mutable 
String=> is immutable: data always stay the same
Ex to clarify:
```
let string= "abc"
let arr= ['a', 'b', 'c']
arr[0]= 'b'; //arr will be ['b', 'b', 'c']
string[0]= 'b'; //string will stay "abc"
```

## ✨️ Third: Objects
**Objects collect multiple values together**

### 👩‍💻 Code Examples:
```
//Creat Object
const person ={
  name: "Safa",
  country: "Palestine",
  age: 20
}
```

### 📝 Notes:
* You can access any attribute in the object by using dot notation, ex: ```let personName=person.name //personName will be Safa```
* Object.freeze() make object immutable.
* Properties in object can be a function and in this case we called it method.
* There is built in object like console/ document/ Math.

# 💪 Challenge Solutions:
[Fisrt challenge: profile-lookup](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/profile-lookup)
```
// Setup
const contacts = [
  {
    firstName: "Akira",
    lastName: "Laine",
    number: "0543236543",
    likes: ["Pizza", "Coding", "Brownie Points"],
  },
  {
    firstName: "Harry",
    lastName: "Potter",
    number: "0994372684",
    likes: ["Hogwarts", "Magic", "Hagrid"],
  },
  {
    firstName: "Sherlock",
    lastName: "Holmes",
    number: "0487345643",
    likes: ["Intriguing Cases", "Violin"],
  },
  {
    firstName: "Kristian",
    lastName: "Vos",
    number: "unknown",
    likes: ["JavaScript", "Gaming", "Foxes"],
  },
];

function lookUpProfile(name, prop) {
  // Only change code below this line
  let contact= contacts.find(element=> element.firstName===name )
    if (!contact){
        return "No such contact"
    }
    if(!contact.hasOwnProperty(prop)){
        return "No such property";
    }
    return contact[prop]
  // Only change code above this line
}

lookUpProfile("Akira", "likes");
```
[Second challenge: copy-array-items-using-slice](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-data-structures/copy-array-items-using-slice)
```
function forecast(arr) {
  // Only change code below this line
  const arr1=arr.slice(2,4);
  return arr1;
}

// Only change code above this line
console.log(forecast(['cold', 'rainy', 'warm', 'sunny', 'cool', 'thunderstorms']));
```
[Third challenge: combine-arrays-with-the-spread-operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-data-structures/combine-arrays-with-the-spread-operator)
```
function spreadOut() {
  let fragment = ['to', 'code'];
  let sentence=['learning', ...fragment, 'is', 'fun']; // Change this line
  return sentence;
}

console.log(spreadOut());
```


