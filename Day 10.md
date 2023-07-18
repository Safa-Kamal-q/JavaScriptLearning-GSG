<h1 align="center">🚀 Day 10 </h1>

 # course: [Deep JavaScript Foundations, v3](https://frontendmasters.com/courses/deep-javascript-v3/)
**# [Slides](https://static.frontendmasters.com/resources/2019-03-07-deep-javascript-v2/deep-js-foundations-v2.pdf)**

**# [Java Script specification](https://262.ecma-international.org/9.0/#Title)**

 # 🔎 Topics:
 **1. Intoduction**

 **2. Primitive && Object data type**

 **3. undefined vs. undeclared vs. uninitialized (aka TDZ)**

 **4. Special Values**

 ## ✨️ First: Intoduction
 **This course is really trying help us to understand the algorithm the DNA of JS**
 
 📌 **Whenever there's a divergence between what your brain thinks is happening, and what the computer does, that's where bugs enter the code.**

 ### 📝 Example to see the importance of knowing how the code run:
 ```
var x="5"
x=x+1 //x:51
x++ //x:51
x //x:52 
```
* We all know that x++ equals to x=x+1 but in this code the result of them are different and if we see how x++ run, we will understand what happened...
* left hand side expression make two operator:
    1. convarte the data type into number
    2. increment the value by 1


 ## ✨️ Second: Primitive && Object data type
  ### 📝 Notes:
  1. In JavaScript, everything is an object."? 💭🤔
      * No, not excatly but they say that since everything in JS can behave as object
  2. Primitive object:
      • undefined
      • string
      • number
      • boolean
      • bigint 
      • symbol
3. In JavaScript, variables don't have types, values do
     * When we use typeof() method we don’t ask about what is the type of variable but we ask about what is the type of value that this variable has.
     * typeof() always return a string, be carful when use it in === operator
  
 ## ✨️ Third: undefined vs. undeclared vs. uninitialized (aka TDZ)
 **Undeclared:** means that it is never been declared in the scope that we look for 
 
 **Undefined:** means there is definitly a variable and at the moment it has no variable 
 
 **Uninitialized:** variable that never been intialized, TDZ: Temporal dead zone 

  ## ✨️ Forth: Special Values 
  ### ⚈ NaN 
    #### 📝 Notes:
    1. it is not mean not a nnumber it is mean invalid number 
    2. NaN are not equal to each, ex: 
      ```
      var age= ('s'/2); //this will make age NaN
      age === age //false
      ```
   3. ```isNaN("I am Safa")  //true``` we all know that the string is not a number but also we know that this string is not an invalid number so in ES6 they solve this problem by ```Number.isNaN("I am Safa") //false```

 ### ⚈ negative zero -0

  ### ⚈ Fundamental Objects
  **Bulit-in object, Native function**
  #### 📝 Notes:
  Use new: 
  • Object()
  • Array()
  • Function()
  • Date()
  • RegExp()
  • Error()
  
  don't use new:
  • String()
  • Number()
  • Boolean()

 ## ✨️ Exercise:
 ```
// TODO: define polyfill for `Object.is(..)`

if (!Object.is || true){   // to disaple the built in method & build my own
    Object.is = function ObjectIs(x,y){
        const xNegZero = isItNegZero(x)
        const yNegZero = isItNegZero(y)

        if (yNegZero || xNegZero ){
            return yNegZero && xNegZero
        }else if (isItNane(x) && isItNane(y)){
            return true
        }else {
            return x===y
        }

        function isItNegZero(v){
            return v===0 && (1/v)=== -Infinity
        }

        function isItNane(v){
            return v !==v
        }
    }
} 

// tests:
console.log(Object.is(42,42) === true);
console.log(Object.is("foo","foo") === true);
console.log(Object.is(false,false) === true);
console.log(Object.is(null,null) === true);
console.log(Object.is(undefined,undefined) === true);
console.log(Object.is(NaN,NaN) === true);
console.log(Object.is(-0,-0) === true);
console.log(Object.is(0,0) === true);

console.log(Object.is(-0,0) === false);
console.log(Object.is(0,-0) === false);
console.log(Object.is(0,NaN) === false);
console.log(Object.is(NaN,0) === false);
console.log(Object.is(42,"42") === false);
console.log(Object.is("42",42) === false);
console.log(Object.is("foo","bar") === false);
console.log(Object.is(false,true) === false);
console.log(Object.is(null,undefined) === false);
console.log(Object.is(undefined,null) === false);
```
# 💪 Challenge Solutions:
## Questions: [Learning sprint (1), week (3), day (1) delieverables](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day1-tasks/tasks.md)

**Q1 solution**
```
function convertStringToNumber(input){
    return typeof input==="string"? input++: {value: input, type: typeof input} 
}
```

**Q2 solution**
```
const checkNaN = value => Number.isNaN(value)
```

**Q3 solution**
```
function isEmptyValue(input) {
    return input === undefined? "undefined": input === null? "null": "Empty string";
  }
```

**Q4 solution**
```
const complexCoercion = (input) => {
    if (typeof input === 'number') {
      return Boolean(input.toString());
    } else if (typeof input === 'string') {
      return Boolean(input);
    } else if (input === null || input === undefined) {
      return false;
    } else {
      return input;
    }
  };
```
