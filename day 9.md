 <h1 align="center">🚀 Day 9 </h1>

 # course: [JavaScript: The Hard Parts, v2](https://frontendmasters.com/courses/javascript-hard-parts-v2/)

  # 🔎 Topics:
  **1. Introduction**
  
  **2. Generate objects using a function**

  **3. Using the prototype chain**

  **4. Using new Keyword**

  **5. Class**


## ✨️ First: Introduction:
**Reminder**
  - Core of development (and running code)
      1. Save data (e.g. in a quiz game the scores of user1 and user2)
      2. Run code (functions) using that data (e.g. increase user 2’s score)

**Why we use OOP**
  - We want my code to be:
    1. Easy to reason about
    2. Easy to add features to (new functionality)
    3. Nevertheless efficient and performant
  - So the Object-oriented paradigm aims is to let us achieve these three goals
  - Ex. to clarrify: imagne that we have a 100 user and every user has name, score, functions, so if i will make an object for every user separately, the code will have a lot of redundant so how we can fix it?we will take about 4 solution 

## ✨️ Second: Solution1=>Generate objects using a function

```
function userCreator(name, score) {
 const newUser = {};
 newUser.name = name;
 newUser.score = score;
 newUser.increment = function() {
 newUser.score++;
 };
 return newUser;
};
const user1 = userCreator("Will", 3);
const user2 = userCreator("Tim", 5);
user1.increment()
```
### 📝 Notes:
1. **Problems with this solution:**
     - Each time we create a new user we make space in our computer's memory for all our data and functions. But our functions are just copies
     - When I want to add attribute, I must add it manually to every user
2. **Benefits:** It's simple and easy to reason about!

## ✨️ Third: Solution2=>Using the prototype chain
```
function userCreator (name, score) {
 const newUser = Object.create(userFunctionStore);
 newUser.name = name;
 newUser.score = score;
 return newUser;
};
const userFunctionStore = {
 increment: function(){this.score++;},
 login: function(){console.log("Logged in");}
};
const user1 = userCreator("Will", 3);
const user2 = userCreator("Tim", 5);
user1.increment();
```
### 📝 Notes:
1. **What we must do?**
     - Store the increment function in just one object and have the interpreter, if it doesn't find the function on user1, look up to that object to check if it's there
     - Link user1 and functionStore so the interpreter, on not finding .increment, makes sure to check up in functionStore where it would find it
     - Make the link with Object.create() technique
  
2. **What if we want to confirm our user1 has the property score**
    - I can use hasOwnProperty() ex: ```user1.hasOwnProperty('score') ```
    - Why JS allows user1 to use this function ?
        * Every object has a default hidden __proto__ property on it and it is linking with Object.prototype object(that has this function and alot) 
        * If the object take another (__proto__) property link to something insteade of link to Object.prototype, the default __proto__ will deleted
        * When I declare user1 in this solution, the Object.create(userFunctionStore) make user1 has __proto__ than link to userFunctionStore 
        *  So first JS look for this method in user1 and it dose not find it so it look for it in userFunctionStore by using the link and it will not find it so it look for it in the Object.prototype and finally it find it
3. **this keyword**
   1. When I use this in userFunctionStore function, this will point to user1
   2. What if I declare a function inside userFunctionStore and use this, ex:
        ```
        const userFunctionStore = {
         increment: function() {
         function add1(){ this.score++; }
         add1()
         }
        };
        ```
        in this case this will point for window in the console
   3. Rule: Any function that's being run to the right hand side of the dot whatever the left hand side that's going to be the list assignment(this will point for left hand on dot) But when there's no dot. It defaults the global to the window(this will point to the window)
      * Unless that function was defined as an arrow function
      * to clarrify:
          ```
         const userFunctionStore = {
         increment: function() {
         const add1 = ()=>this.score++;
          add1()
         }
        };
        ```
      * Rule: this in arrow function point to where it was stored
  4. **Problem in this solution:** No problem but the programmer don't use it often

## ✨️ Forth: Solution3=>Using new Keyword
```
function userCreator(name, score) {
  this.name = name;
  this.score = score;
};
userCreator.prototype // {};
userCreator.prototype.increment = function(){
 this.score++;
}
const user1 = new userCreator("Will", 3);
```
### 📝 Notes:
1. Functions are both objects and functions
   * We could use the fact that all functions have a default property `prototype` on their object version, (itself an object) - to replace our `functionStore` object
2. Benefits for using this solution: faster to write. Often used in practice in professional code.
3. Problems: We have to upper case first letter of the function so we know it requires ‘new’ to work!
4. what new keyword do:
![Screenshot (125)](https://github.com/Safa-Kamal-q/Mastering-JavaScript-in-20-Days/assets/119218518/86add149-e05e-4fa3-97c2-0d0ef137b29a)


## ✨️ Fifth: Solution4=>Using class keyword 
**class is a syntax suger**
```
class UserCreator {
 constructor (name, score){
 this.name = name;
 this.score = score;
 }
 increment (){ this.score++; }
 login (){ console.log("login"); }
}
const user1 = new UserCreator("Eva", 9);
user1.increment();
```
### 📝 Notes:
1. Under the hood class do what new do to make the object 

# 💪 Challenge Solutions:
[Tap here to see my freeCode account](https://www.freecodecamp.org/Safa_Qasrawi)
