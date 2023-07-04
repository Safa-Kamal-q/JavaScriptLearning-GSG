<h1 align="center">🚀 Day 2 </h1>

# course: [JavaScript: From First Steps to Professional](https://frontendmasters.com/courses/javascript-first-steps/)

# 🔎 Topics:
**1. DataType**

**2. String**

**2. Operator**

## ✨️ First: DataType In general
**There is two different kind of data type in JS:**
1. Primitive data type (string, number, bigint, boolean, symbol, null and undefined.)
2. Object data type like document

### 📝 Notes:
1. To know the type of an value you can use (typeof) operator.
2. typeof operator returns a string of the data type for the valuse that I look for, ex: ```typeof("Safa") //output: "string"```
3. There is a different between null&undifined. In general: null=>when you want someething to be null. undefined=>when I expect a data has a value but it doesn’t 
4. null is an object data type but is also primitive dataType

## ✨️ Second: String
**String:** in sequence of zero or more character

**Index:** is a number assigned to  the positions of String's character 

### String method:
* To know the index of a character in a string or from any index a substring bgin in a specific string I can use indexOf, ex: ```document.title.indexOf("sa") //will output a number``` if the character or the substring doesn't exist it will output -1.
* To know if a string include a specific substring, use includes, ex: ```"Safa".includes("Sa") //will return a boolean```
* To know if a string start with a specific substring, use startWith, ex: ```document.getElementById("p1-symbol").textContent.startsWith("Sa") //will return boolean```
* toLowerCase()=> To make the character small, toUpperCase()=>To make the character upper
* use + operator to contacten two string.

### 📝 Notes:
1. Spaces are not ignore in JS and every space is consider a character
2. JavaScript strings are considered a primitive datatype, which means they are not objects.
3. When I want to reach to any character in a string I can use [write the index of a character]
4. JS is case sensitive

## ✨️ Third: Operator
**TThere is a lot of operator but I will mention the importants one.**
### Arithmatic Operation:
1. (+) Add
2. (-) Subtract
3. (/) Divide
4. (*) Multiblicate

### comparison Operator
1. (>) greater than
2. (<) smaller than
3. (>=) greater than or equal to
4. (<=) smaller than or equal to

### Equality Operator 
| Strict | Loosey-goosey | Meaning |
| ----------- | ----------- | ----------- |
| === | == | equals |
| !== | != | not equals |

#### 📝 Notes in equality:
when you use Loosey-goosey operator, it will output true if you compare 1 & "1" because this make casting to make the dataType the same and then compare so be careful and always use strict operator.


