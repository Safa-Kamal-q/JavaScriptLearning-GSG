<h1 align="center">🚀 Day 12 </h1>

# course: [JavaScript: The Hard Parts, v2](https://frontendmasters.com/courses/javascript-hard-parts-v2/)

# 🔎 Topics:
**1. Function Expression**

**2. Advanced Scope**

## ✨️ First: Function Expression:

### 📝 Notes:
**function expression: it is all statment in the code has a function keyword but it is not in the start of the statment code** 
**Function expresion vs. declaration:**

Function declaration : is that function declaration and their name they attach their marble to the enclosing scope.

Function expression: add their marble to their own scope

**Benefits of expression:** it is not hoisted, so you can’t use them before they are defined in your code. This helps if you want to make sure that a function is only used after it is defined.
```
let myFunction= function sayHello(){console.log("Hello")}
myFunction() //it will print hello
sayHello() //refrence error
```
**By using eexpression we can make an anonymous function**

## ✨️ Second: Advanced Scope**
### 📝 Notes:
**Lexical vs. Dynamic scope**

lexical scope: complier time/ where function declare 

dynamic scope: run time/ where function excute or call/  the variable takes the value of the most latest value assigned to that variable 

[Tap here, this video can help](https://www.youtube.com/watch?v=BwxbW6csvNQ)

**IIEF: (Immediately Invoked Function Expression)** a function that runs the moment it is invoked or called in the JavaScript event loop.
```
(function sayHello(name){
  console.log("hello ", name)
})("Ahmad")
```

# 💪 Challenge Solutions:
[Tap here to see questions](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day3-tasks/tasks.md)

Q1 solution:
```
const arrowHOF = (normalFunc) => {
  return (...args) => {
    return (...multiplierArgs) => {
      const numTimes = multiplierArgs.reduce((acc, val) => acc * val, 1);
      const result = [];

      for (let i = 0; i < numTimes; i++) {
        result.push(normalFunc(...args));
      }

      return result;
    };
  };
};
```

Q2 solution:
```
const preserveThis = (func) => {
  return (...args) => {
    func.call(this, ...args);
  };
};
```

Q3 soolution:
EX1: 
1. We call outer1
2. We declare x variable by using vat that mean that x in now has function scope  
3. We use function expression: assign anonymous function into inner1 variable so we can use inner1 as a function
4. call inner1 so it output 10 

