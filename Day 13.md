<h1 align="center">🚀 Day 13 </h1>

# course: [JavaScript: The Hard Parts, v2](https://frontendmasters.com/courses/javascript-hard-parts-v2/)

# 🔎 Topics:
**1. Clousers**

**2. Moduls**

## ✨️ First: Clousers:
**Closure:** is when a function “remembers” its lexical scope even when the function is executed outside that lexical scope.

### 📝 Notes:
**Clousers: loop**
```
for (var i=1; i<=3; i++){
    setTimeout(()=>{
        console.log(`i ${i}`)
    },1000*i)
}
// i 4
// i 4
// i 4 
```
since we use var, it will be only one i for all iteration so after timeOut delay it will have just the last value 

```
for (let i=1; i<=3; i++){
    setTimeout(()=>{
        console.log(`i, ${i})
    },1000*i)
}
// i, 1
// 1, 2
// i, 3
```
since we declare i by using let this will make seperate i for every iteration.

## ✨️ Second: Modules:
Modules encapsulate data and behavior (methods) together. The state (data) of a module is held by its methods via closure.
### 📝 Notes:
1. namespace is not a module since it is not has encapsulation


# 💪 Challenge Solutions:
[Tap here to see questions](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day4-tasks/tasks.md)


Q1 solution:

This output because that setTimeOut is an asynchronous function. When the loop runs, it schedules five setTimeout callbacks, each with a delay of 100 milliseconds. However the loop don't wait for the de;ay so it give the i the last value which is 5

to fix it:

```
for (var i = 0; i < 5; i++) {
  let j= i;
    setTimeout(function() {
      console.log("value of [i] is: ", j);
    }, 100);
}
```

Q2 solution:
in this code the array will be declaring in every iteration in the loop 
```
let  array = [];
for (let i = 0; i < 5; i++) {

    array.push(i);
    
 }
 console.log("Current array is: ", array)
 ```

Q3 solution:
```
let functions = [];

for (let i = 0; i < 5; i++) {

  functions.push(() => {
    console.log("Current value of i is:", i);
  });
}

functions.forEach((func) => func());
```

**Clouser Questions**


Q1 solution:
```
function privateCounter() {
  let count = 0;

  function increment() {
    count++;
  }

  function getCount() {
    return count;
  }

  return {
    increment: increment,
    getCount: getCount
  };
}
```

Q2 solution:
```
function generateFibonacci(count) {
  let currentCount = 0;
  let prevNumber = 0;
  let currentNumber = 1;

  function getNextFibonacci() {
    if (currentCount >= count) {
      return null;
    }

    const result = prevNumber;
    const nextNumber = prevNumber + currentNumber;

 
    prevNumber = currentNumber;
    currentNumber = nextNumber;
    currentCount++;

    return result;
  }

  return getNextFibonacci;
}
```
