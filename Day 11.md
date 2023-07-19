<h1 align="center">🚀 Day 11 </h1>

# course: [JavaScript: The Hard Parts, v2](https://frontendmasters.com/courses/javascript-hard-parts-v2/)

# 🔎 Topics:
**1. Static Typing**

**2. Scope**

## ✨️ First: Introduction:
### 📝 Notes:
⚈ Benefits:
1. Catch type-related mistakes
2. Communicate type intent
3. Provide IDE feedback

⚈ TypeScript & Flow
ex:
```
let name: string = "safa"
name= {fName: "safa"} //Error cannot asign object to string
```
📌 Notes:
1. In type script when I assign a value into a variable this variable assign the values's type into the variable for ever
2. Static type inference means that in typeScript when I assign a value into a variable typeScript will make this variable only hold value's data type 
3. I can make special data type:
   * ex:
   * ```
     let student={name: string}
     let studentOne: student = {name: "safa"};
     ```
4. [Type script vs. Flow](https://github.com/niieani/typescript-vs-flowtype)

## ✨️ Second: Scops:
**scope:  the area where a function or variable is visible and accessible to other code**
### 📝 Notes:
1. JavaScript organizes scopes with functions and blocks
2. Js ix lexical scope language all the scops that we dealing with that all determined at compiler time not run time 
3. In our processor phase, compilation phase we have scope manager and compiler 
      * Scope manager: the process whereby the outputs, outcomes and benefits are identified, defined and controlled.
4. When JS need to excute a code first it is look for this value in this scope if JS doesn’t find it, will search in the bigger scope.
5. In call statement: the virtual machine(JS engine) ask the global scope if there is this function, the function name is source reference and after finding the function in line 9 for example, the execution go to line 9 and in the function will not be the declaration ketword like var instead of it will have a target refrence for variable
6. When I try to call something not a function it will fire type error  ex:```let name= "safa"; name()//will throw type error ```
7. In a function if we don’t declare a variable and just assign a value to it, JS will declare a variable in global scope but if we are in strict mode it will throw a refrence error 
8. To use strict mode write "use strict" at the top of the file 
    * ex:
      ```
       function sayHello(){
       name= "Safa"
       console.log("Hello ", name)
       }
       sayHello()
       console.log(name)// safa
       // "use strict" if I declare it at the top of the file it will be as the following
       console.log(name) //reference error
      ```
9. Having two varibles with same name in different scopes called shadowing

# 💪 Challenge Solutions:
[Tap here to see the questions](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week3-day2-tasks/tasks.md)

Q1: I will ask about it 

**Q2 solution:**
The answer will be C: because var has function scope and var in not blocked scope, but let,ver is blocked scope 

**Q3 solution**
The output will be: undifined , refrenceError, refrenceError: since var declarations are hoisted to the top of their scope during the creation phase. However, only the declaration is hoisted, not the initialization. So, at this point, a exists but has the value undefined. However let & const is not a hoisting declaration and they are blocked scope 

**Q4 solution**
The answer will be C: the same explanation 
