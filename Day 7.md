 <h1 align="center">🚀 Day 7 </h1>

 # course: [JavaScript: The Hard Parts, v2](https://frontendmasters.com/courses/javascript-hard-parts-v2/)

  # 🔎 Topics:
  **1. Closure**

  ## ✨️ First: Closure:
  **A closure is a function having access to the parent scope, even after the parent function has closed.**
  
  **Intro:**
  
    * When our functions get called, we create a live store of data (local memory/variable environment/state) for that function’s execution context.
    * When the function finishes executing, its local memory is deleted (except the returned value)
    * So what if we want to make a function hold on to live data between executions 

  ### 📝 Notes:
  1. Calling a function in the same function call as it was defined
      * When I declare an inner function in the outer function the inner one can access of the attribute of outer function, scope of outer function called by lexical scope
  2. When the outer function returned an inner function and in the inner function there is code use attribute from the outer one, it doesn't return the inner function only also it returns it's backpack [[scope]] that has the outer's attribute that used in inner function
  3. If we run 'outer' again and store the returned 'incrementCounter' function definition in 'anotherFunction', this new incrementCounter function was created in a new execution context and therefore has a brand new independent backpack
       ```
        // to clarrify the idea 
       function outer (){
         let counter = 0;
         function incrementCounter (){
         counter ++;
         }
         return incrementCounter;
        }
       const myNewFunction = outer();
        myNewFunction();
        myNewFunction();
        const anotherFunction = outer();
        anotherFunction();
        anotherFunction();
       ````


# 💪 Challenge Solutions:
[Tap here to see the questions](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day2-tasks/tasks.md)

**Q1 solution:**

  ```
  const createCounter= start =>{
      return function(){
          start++
          console.log(start)
      }
  }
  ```
**Q2 solution:**
```
const calculateAverage= nums =>{
    return function() {
        let sum=0;
        nums.forEach(element => {
            sum+=element
            
        });
        return sum/nums.length
    }
}
```

**Q3 solution:**
```
const powerOf= base => {
    return function(exp){
        return Math.pow(base, exp);
    }
}
```

**Q4 solution:**
```
const compose = (...functions) =>{
    return function (value){
        for(let i= functions.length-1; i>=0;i--){
            value = functions[i](value);
        }
        return value;
    }
}
```
