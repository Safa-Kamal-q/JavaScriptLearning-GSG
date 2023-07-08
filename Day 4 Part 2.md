<h1 align="center">🚀 Day 4 Part 2 </h1>

 # course: [JavaScript: From First Steps to Professional](https://frontendmasters.com/courses/javascript-first-steps/)

# 🔎 Topics:
**1. Events & Handlers**

**2. Conditions**

**3. Loops**

**4. Map, Filter & Spread**

**5. Asynchronous function**

## ✨️ First: Events & Handlers
**By using Events we make our interactive**
### 📝 Notes:
* We can detect events in JS by using .addEventListner(“eventName”, ()=>{StatementThatHandleEvent}), this method take the action's name and a handle function that JS call it when the event is fired.
* Everytime JS calls your handler function it is going to pass an event object
   * **target** is from the event object and it tells which element the event fired on
* There is a lot of event that we can handle like(click, dblclick, mouseover …..)

### Code Examples
```
let trueB= optionButtons[0]
trueB.addEventListener('click', ()=>{trueB.textContent=trueB.textContent.toUpperCase()})

let h1 = document.getElementsByTagName("h1")
h1 = h1[0]
h1.addEventListener("mouseover", ()=>{h1.textContent="Quiz page"})
```
## ✨️ Second: Conditions
### 📝 Notes:
* If I put in the condition 0, empty string, undefined & null it is treat as false but empty array treat like true
* **! notation:** If I want the condition to be the opposite of specific value
* **&& notation** If I want two condition be true to run the code
* **|| notation:** If I wwant to run the code even there is only one true condition
* conditional ternary operator: JS also has a shortcut operator for writing quick condition, it need 3 value to work
   * code example:
     ```
     let stringValue = 4<5? "4 smaller than 5": "4 greater than 5"
     ```
## ✨️ Third: Loops
**loop let us run the same code multiple time (iteration)**
### for loop
* We need to declare and initialize variable, and make condition, and change the variable(decrement, increament....)
* ex: ``` for (let t=0; i<arr.length; i++){....} ```
* for …. of loops let us more easily iterate over items in a collection
* We can use for…of with string/ array and every iterative value
* ex: ``` for (let item of arr){....} ``` 

### while loop
When I want to run a code as long as a condition true

ex: ``` while (arr.length> 10){...} ```

## ✨️ Forth: Map, Filter & Spread
**These method let us process all item in an array**

### Filter:
* Filter out the ingredient I don’t want from that array
* Filter call true false function on each item and create a new array with only the item where the function return true
  
### Map: 
* Map applies some kind of operation to everything in that array
  
### spread:
* Spread let us spread the array item one by one

### Code Example 
```
let number =[1,2,3,4, 5, 6, 7, 8, 9]

let filterArr=number.filter (item => item>5); //[6, 7, 8, 9]

let mapArr= number.map(item => item*2); //[2, 4, 6, 8, 10, 12, 14, 16, 18]

let spreadArr=[0, ...number, 10] // [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```


## ✨️ Fifth: Asynchronous function
### 📝 Notes:
* JS in general is synchronous function, excute line by line
* But when we have a code that will have a lot of time to excute I can make the code asynchronous(does not wait a lot for an asynchronous code and excute the code bellow it that does not effect in the result of asynchronous code)

# 💪 Challenge Solutions:
[First challenge: use-the-filter-method-to-extract-data-from-an-array](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-the-filter-method-to-extract-data-from-an-array)
```
// The global variable
const watchList = [
  {
    "Title": "Inception",
    "Year": "2010",
    "Rated": "PG-13",
    "Released": "16 Jul 2010",
    "Runtime": "148 min",
    "Genre": "Action, Adventure, Crime",
    "Director": "Christopher Nolan",
    "Writer": "Christopher Nolan",
    "Actors": "Leonardo DiCaprio, Joseph Gordon-Levitt, Elliot Page, Tom Hardy",
    "Plot": "A thief, who steals corporate secrets through use of dream-sharing technology, is given the inverse task of planting an idea into the mind of a CEO.",
    "Language": "English, Japanese, French",
    "Country": "USA, UK",
    "Awards": "Won 4 Oscars. Another 143 wins & 198 nominations.",
    "Poster": "http://ia.media-imdb.com/images/M/MV5BMjAxMzY3NjcxNF5BMl5BanBnXkFtZTcwNTI5OTM0Mw@@._V1_SX300.jpg",
    "Metascore": "74",
    "imdbRating": "8.8",
    "imdbVotes": "1,446,708",
    "imdbID": "tt1375666",
    "Type": "movie",
    "Response": "True"
  },
  {
    "Title": "Interstellar",
    "Year": "2014",
    "Rated": "PG-13",
    "Released": "07 Nov 2014",
    "Runtime": "169 min",
    "Genre": "Adventure, Drama, Sci-Fi",
    "Director": "Christopher Nolan",
    "Writer": "Jonathan Nolan, Christopher Nolan",
    "Actors": "Ellen Burstyn, Matthew McConaughey, Mackenzie Foy, John Lithgow",
    "Plot": "A team of explorers travel through a wormhole in space in an attempt to ensure humanity's survival.",
    "Language": "English",
    "Country": "USA, UK",
    "Awards": "Won 1 Oscar. Another 39 wins & 132 nominations.",
    "Poster": "http://ia.media-imdb.com/images/M/MV5BMjIxNTU4MzY4MF5BMl5BanBnXkFtZTgwMzM4ODI3MjE@._V1_SX300.jpg",
    "Metascore": "74",
    "imdbRating": "8.6",
    "imdbVotes": "910,366",
    "imdbID": "tt0816692",
    "Type": "movie",
    "Response": "True"
  },
  {
    "Title": "The Dark Knight",
    "Year": "2008",
    "Rated": "PG-13",
    "Released": "18 Jul 2008",
    "Runtime": "152 min",
    "Genre": "Action, Adventure, Crime",
    "Director": "Christopher Nolan",
    "Writer": "Jonathan Nolan (screenplay), Christopher Nolan (screenplay), Christopher Nolan (story), David S. Goyer (story), Bob Kane (characters)",
    "Actors": "Christian Bale, Heath Ledger, Aaron Eckhart, Michael Caine",
    "Plot": "When the menace known as the Joker wreaks havoc and chaos on the people of Gotham, the caped crusader must come to terms with one of the greatest psychological tests of his ability to fight injustice.",
    "Language": "English, Mandarin",
    "Country": "USA, UK",
    "Awards": "Won 2 Oscars. Another 146 wins & 142 nominations.",
    "Poster": "http://ia.media-imdb.com/images/M/MV5BMTMxNTMwODM0NF5BMl5BanBnXkFtZTcwODAyMTk2Mw@@._V1_SX300.jpg",
    "Metascore": "82",
    "imdbRating": "9.0",
    "imdbVotes": "1,652,832",
    "imdbID": "tt0468569",
    "Type": "movie",
    "Response": "True"
  },
  {
    "Title": "Batman Begins",
    "Year": "2005",
    "Rated": "PG-13",
    "Released": "15 Jun 2005",
    "Runtime": "140 min",
    "Genre": "Action, Adventure",
    "Director": "Christopher Nolan",
    "Writer": "Bob Kane (characters), David S. Goyer (story), Christopher Nolan (screenplay), David S. Goyer (screenplay)",
    "Actors": "Christian Bale, Michael Caine, Liam Neeson, Katie Holmes",
    "Plot": "After training with his mentor, Batman begins his fight to free crime-ridden Gotham City from the corruption that Scarecrow and the League of Shadows have cast upon it.",
    "Language": "English, Urdu, Mandarin",
    "Country": "USA, UK",
    "Awards": "Nominated for 1 Oscar. Another 15 wins & 66 nominations.",
    "Poster": "http://ia.media-imdb.com/images/M/MV5BNTM3OTc0MzM2OV5BMl5BanBnXkFtZTYwNzUwMTI3._V1_SX300.jpg",
    "Metascore": "70",
    "imdbRating": "8.3",
    "imdbVotes": "972,584",
    "imdbID": "tt0372784",
    "Type": "movie",
    "Response": "True"
  },
  {
    "Title": "Avatar",
    "Year": "2009",
    "Rated": "PG-13",
    "Released": "18 Dec 2009",
    "Runtime": "162 min",
    "Genre": "Action, Adventure, Fantasy",
    "Director": "James Cameron",
    "Writer": "James Cameron",
    "Actors": "Sam Worthington, Zoe Saldana, Sigourney Weaver, Stephen Lang",
    "Plot": "A paraplegic marine dispatched to the moon Pandora on a unique mission becomes torn between following his orders and protecting the world he feels is his home.",
    "Language": "English, Spanish",
    "Country": "USA, UK",
    "Awards": "Won 3 Oscars. Another 80 wins & 121 nominations.",
    "Poster": "http://ia.media-imdb.com/images/M/MV5BMTYwOTEwNjAzMl5BMl5BanBnXkFtZTcwODc5MTUwMw@@._V1_SX300.jpg",
    "Metascore": "83",
    "imdbRating": "7.9",
    "imdbVotes": "876,575",
    "imdbID": "tt0499549",
    "Type": "movie",
    "Response": "True"
  }
];

// Only change code below this line

const filteredList = watchList.filter(item=> parseFloat(item.imdbRating)>=8.0)
.map(movie=> ( 
  {
  title: movie.Title,
  rating: movie.imdbRating
}))

// Only change code above this line

console.log(filteredList);
```
[Second challenge: golf-code](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/golf-code)
```
const names = ["Hole-in-one!", "Eagle", "Birdie", "Par", "Bogey", "Double Bogey", "Go Home!"];

function golfScore(par, strokes) {
  // Only change code below this line
  if (strokes === 1) {
    return names[0];
  } else if (strokes <= par - 2) {
    return names[1];
  } else if (strokes === par - 1) {
    return names[2]; 
  } else if (strokes === par) {
    return names[3]; 
  } else if (strokes === par + 1) {
    return names[4]; 
  } else if (strokes === par + 2) {
    return names[5]; 
  } else {
    return names[6]; 
  }

  // Only change code above this line
}

golfScore(5, 4);
```
[Third challenge: use-multiple-conditional-ternary-operators](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/use-multiple-conditional-ternary-operators)
```
function checkSign(num) {
  return num===0? "zero": num>0? "positive": "negative"
}

checkSign(10);
```
