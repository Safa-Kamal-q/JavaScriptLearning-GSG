<h1 align="center">🚀 Day 4 </h1>

 # course: [JavaScript: From First Steps to Professional](https://frontendmasters.com/courses/javascript-first-steps/)

# 🔎 Topics:
**1. Quiz and Project**

**2. Function**

**3. Scope**

## ✨️ First: Quiz & Project 

### ⚈ [Quiz](https://anjana.dev/javascript-first-steps/2-jsquiz-fancy.html)

### ⚈ Project
```
<!DOCTYPE html>
<!-- saved from url=(0063)https://anjana.dev/javascript-first-steps/2-jsquiz-starter.html -->
<html lang="en-US">

<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">

    <title>Quiz.js</title>
    <style>
        body {
            margin: 1rem auto;
            padding: 3rem;
            font-family: sans-serif;
        }

        header {
            width: 50%;
            margin: 1em auto;
        }

        main {
            min-width: 25rem;
            max-width: 50%;
            margin: 0px auto;
            display: flex;
            flex-direction: column;
        }

        #statement {
            border: 1px solid black;
            border-radius: 0.5rem;
            box-shadow: 5px 5px 5px gray;
            padding: 1rem;
            font-size: x-large;
            text-align: center;
            margin: 1rem 0px;
            min-height: 2em;
        }

        #explanation {
            padding: 1rem;
            text-align: center;
        }

        #options {
            width: 100%;
            display: flex;
            flex-direction: column;
        }

        button {
            padding: 0.5rem;
            font-size: medium;
            border-radius: 5px;
        }

        .correct {
            background-color: lightgreen;
        }

        .incorrect {
            background-color: lightpink;
        }
    </style>
</head>

<body>
    <header>
        <h1>Quiz.js</h1>
        <p>Do you know JS? Find out!</p>
    </header>

    <main>
        <div id="statement">

        </div>

        <div id="options">
            <button name="true" value="57">57</button>
            <button name="false" value="327">327</button>
        </div>

        <div id="explanation">

        </div>

    </main>

    <script type="text/javascript">

        // TODO 1: Declare & assign variables pointing to the corresponding element(s)
        // statement should be the "statement" div
        // optionButtons should be all the elements within the "options" div
        // explanation should be the "explanation" div

        const statement = document.getElementById('statement');
        /*const optionButtons= document.querySelectorAll('button');  this will bring any button even it is outside the div */
        const optionButtons = document.querySelector('#options').children
        const explanation = document.querySelector("#explanation");

        // TODO 2: Declare & assign a variable called fact
        // Its value should be an object with a statement, true/false answer, and explanation 
        const fact = {
            statement: "What would be the result of 3+2+”7″?",
            answer: "57",
            explanation: "Since 3 and 2 are integers, they will be added numerically. And since 7 is a string, its concatenation will be done. So the result would be 57."
        }

        // TODO 3: Set the text of the statement element to the fact's statement
        statement.textContent = fact.statement;

        // TODO 4: Declare disable & enable functions to set or remove the "disabled" attribute from a given button element
        // disable(button) should set the button element's attribute "disabled" to the value ""
        // enable(button) should remove the attribute "disabled" from the button element
        const disable = button => { button.setAttribute("disabled", "") }
        const enable = button => { button.removeAttribute("disabled") }

        // TODO 5: Declare an isCorrect function that compares a guess to the right answer
        // isCorrect(guess) should return true if the guess matches the fact's answer
        const isCorrect = guess =>  guess === fact.answer.toString(); 

        // TODO 6A: Use a for loop to add a click event listener to each of the optionButtons
        for (let button of optionButtons) {

            button.addEventListener("click", c => {
                // TODO 6B: Within the event handler function, display the fact's explanation by setting the text of the explanation element
                explanation.textContent = fact.explanation;
                // TODO 7: Within the event handler function, 
                // Use a for loop to disable all the option buttons
                for (let allButtons of optionButtons) {
                    disable(allButtons);
                }

                // TODO 8: Within the event handler function,
                // Get the guessed value from the clicked button
                // Use a conditional to compare the guess to the fact's answer
                // and add the "correct"/"incorrect" class as appropriate
                isCorrect(button.value) ? button.classList.add("correct") : button.classList.add("incorrect");
            })
        }



    </script>

</body>

</html>
```

## ✨️ Second: Function 

### 📝 Notes:
* **Declaring and calling function**
  * Declaring: function functionName (parameter){ statments }
  * Calling: functionName(argument)
* In call statment if I pass more or less arqument that prameter, ut doesn't care in JS (will not throw an error).
* Anonymous function: When I declare a function without name, ex: ``` const sayHello= function (){console.log("Hello")} ```
* Arrow function: we call it in this name since we use this notation(=>)
  * If we have only one parameter it is not necessary to put it between parenthesis ()
  * if we have only return statment, it is not necessary to use return keyword
  * ex: ``` const add= (x,y)=> x+y; ```

## ✨️ Third: Scope
**Scope: the area where a function or variable is visible and accessible to other code**

**Var** Not blocked-scope it is function scope 

**let/ const** function and blocked scope 

# 💪 Challenge Solutions:
[First challenge: stand-in-line](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/stand-in-line)
```
function nextInLine(arr, item) {
  // Only change code below this line
  arr.push(item )
  let elment= arr.shift();
  return elment;
  // Only change code above this line
}

// Setup
let testArr = [1, 2, 3, 4, 5];

// Display code
console.log("Before: " + JSON.stringify(testArr));
console.log(nextInLine(testArr, 6));
console.log("After: " + JSON.stringify(testArr));
```
[Second challenge: global-vs--local-scope-in-functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/global-vs--local-scope-in-functions)
```
// Setup
const outerWear = "T-Shirt";

function myOutfit() {
  // Only change code below this line
  const outerWear= 'sweater'
  // Only change code above this line
  return outerWear;
}

myOutfit();
```
[Third challenge: local-scope-and-functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/local-scope-and-functions)
```
function myLocalScope() {
  // Only change code below this line
  const myVar="SAFA"
  console.log('inside myLocalScope', myVar);
}
myLocalScope();

// Run and check the console
// myVar is not defined outside of myLocalScope
console.log('outside myLocalScope', myVar);
```
[Forth challenge: global-scope-and-functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/global-scope-and-functions)
```
// Declare the myGlobal variable below this line
let myGlobal= 10;
function fun1() {
  // Assign 5 to oopsGlobal here
  oopsGlobal=5;
}

// Only change code above this line

function fun2() {
  let output = "";
  if (typeof myGlobal != "undefined") {
    output += "myGlobal: " + myGlobal;
  }
  if (typeof oopsGlobal != "undefined") {
    output += " oopsGlobal: " + oopsGlobal;
  }
  console.log(output);
}
```
[Fifth challenge: return-a-value-from-a-function-with-return](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/return-a-value-from-a-function-with-return)
```
function timesFive(num){
  return 5*num
}
```
