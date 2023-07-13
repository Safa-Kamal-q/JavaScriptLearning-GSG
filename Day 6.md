 <h1 align="center">🚀 Day 6 </h1>

 # course: [JavaScript: The Hard Parts, v2](https://frontendmasters.com/courses/javascript-hard-parts-v2/)
**# [Slides](https://static.frontendmasters.com/resources/2019-09-18-javascript-hard-parts-v2/javascript-hard-parts-v2.pdf)**

 # 🔎 Topics:
**1. Introduction**

**2. Java Script Principle**

**3. Function**

## ✨️ First: Intoduction
**In this course we will learn about:
1. Principles of JavaScript
2. Callbacks & Higher order functions
3. Closure (scope and execution context)
4. Asynchronous JavaScript & the event loop
5. Classes & Prototypes (OOP)

## ✨️ Second: Java Script Principle
### 📝 Notes:
There are two JS principle:
  * 1.	Thread of execution: goes throw code line by line and run the line 
  * 2.	Sava data in its memory so we can use it later
   
## ✨️ Third: Function
**Function : code we save (define) function and can use (call/invoke/ excute/ run )later with the function’s name and ()**
**Execution contest : created to run the code of a function has 2 parts(JS principle)**

### 📝 Notes:
1. parameter is what we write when we declare a function and argument what we write in call statement
2. Call Stack:
   * JavaScript keeps track of what function is currently running (where’s the thread of execution)
      - Run a function - add to call stack
      - Finish running the function - JS removes it from call stack
      - Whatever is top of the call stack that’s the function we’re currently runnin
3. Callbacks vs Higher order function:
     * Callbacks: the inner function
     * Higher order function: the outer function
4. Instead of repering function I can make inner function, ex:
     ```
     function copyArrayAndManipulate(array, instructions) {
     const output = [];
     for (let i = 0; i < array.length; i++) {
     output.push(instructions(array[i]));
     }
     return output;
    }
    function multiplyBy2(input) { return input * 2; }
    const result = copyArrayAndManipulate([1, 2, 3], multiplyBy2);
    ```
    * We can do that since:
    * Functions in javascript = first class objects
    * They can co-exist with and can be treated like any other javascript object
        1. Assigned to variables and properties of other objects
        2. Passed as arguments into functions
        3. Returned as values from functions

5. I can write function in arrow way and this way is mentioned before in first course

# 💪 Challenge Solutions:
[First challenge: use-higher-order-functions-map-filter-or-reduce-to-solve-a-complex-problem](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-higher-order-functions-map-filter-or-reduce-to-solve-a-complex-problem)
```
const squareList = arr => {
  // Only change code below this line
  let arr1= arr.filter(item=> item>0&& Number.isInteger(item)).map(item=> item*item)
  return arr1;
  // Only change code above this line
};

const squaredIntegers = squareList([4, 5.6, -9.8, 3.14, 42, 6, 8.34, -2]);
console.log(squaredIntegers);
```
[Second challenge: apply-functional-programming-to-convert-strings-to-url-slugs](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/apply-functional-programming-to-convert-strings-to-url-slugs?messages=success%5B0%5D%3Dflash.signin-success)
```
// Only change code below this line
function urlSlug(title) {
  return title.toLowerCase().split(" ").filter(word => word !== "").join("-");
}

// Only change code above this line
urlSlug("A Mind Needs Books Like A Sword Needs A Whetstone");
```
[Third challenge: Learning sprint (1), week (2), day (1) delieverable](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day1-tasks/tasks.md#question-2-call-stack-and-recursion)

**First Q**
```
const mapAsync = async (arr, callback) => await Promise.all(arr.map(callback));

const multipleBy2 = (num) => {
    return new Promise(resolve => {
        setTimeout(() => {
            resolve(num * 2);
        }, 1000);
    })
}
```

**Second Question**
```
const sumRange1 = ((start, end)=>{
   return  start===end? start: start+ sumRange(start+1, end)
})
```

