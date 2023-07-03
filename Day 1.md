 <h1 align="center">🚀 Day 1 </h1>

 # course: [JavaScript: From First Steps to Professional](https://frontendmasters.com/courses/javascript-first-steps/)

 # 🔎 Topics:
 1. Introduction
 2. Document Object Model(DOM)

## ✨️ First: Intoduction 
**In this section I learnt about javaScript(JS) in general and where I can run JS code.**
### 📝 Notes:
1. JS is dynamic and web programming landuage
2. JS is compilation target which mean that JS can translate other languages to run in web like typeScript
3. I can run JS code in connsole or on run server like node.js

## ✨️ Second: DOM 
**I leart how to access the HTML elements and how to change the web page.**
### Code Examples:
#### ⚈ Access the HTML element:
```
document.title //will show the page title
document.body //the body element in Html
document.getElementById(“IdName”) //this will bring the first element from HTML that its elementId same as the idName
document.querySelector("#board") //this as the previous but different syntax from CSS suntax
document.getElementByTagName(“tagName”) //will bring all the tags in HTML which has the same as tagName(like h1)
document.querySelectorAll(“tagName”) //the same as the previous
document.getElementByClassName(“className”) //get all element in this class that its name same as the className 
document.querySelectorAll(“.className") //the same as previous
document.getElementById(“IdName”).textContent //will bring the text inside the element that has the id that I wrote
document.querySelector(“h2”).textContent //if we don't have an ID for specific element and we want to reach it 
```
#### ⚈ Change the web page:
```
document.title= “newTitle”
document.getElementById(“IdName”).textContent= “anyTextIWant” //This will delete the previous and write the new Text
document.getElementById(“IdName”).append("Text that I want to add next to the original Text")
```
### 📝 Notes:
1. document by itself: special built in object in Js that represent the whole page(document)
2. When I write the code in console to change the web page and then refresh the page,it will go back to the general form

 # 🔗 Link Can Help
 [In this web you can search about any JS syntax code you want](https://developer.mozilla.org/en-US/)

# 💪 Challenge Solutions:
[First Challenge: Compound Assignment With Augmented Multiplication](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/compound-assignment-with-augmented-multiplication)
```
let a = 5;
let b = 12;
let c = 4.6;

// Only change code below this line
a *= 5;
b *= 3;
c *= 10;
```
[Second challenge: concatenating-strings-with-the-plus-equals-operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/concatenating-strings-with-the-plus-equals-operator)
```
let myStr = "This is the first sentence. ";
myStr += "This is the second sentence.";
```
[Third challenge: Use Bracket Notation to Find the Nth-to-Last Character in a String](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/use-bracket-notation-to-find-the-nth-to-last-character-in-a-string)
```
// Setup
const lastName = "Lovelace";

// Only change code below this line
const secondToLastLetterOfLastName = lastName[lastName.length -2]; // Change this line
```

