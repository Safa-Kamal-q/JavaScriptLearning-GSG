 <h1 align="center">🚀 Day 5 </h1>

 # course: [JavaScript: From First Steps to Professional](https://frontendmasters.com/courses/javascript-first-steps/)#

# 🔎 Topics:
 **1. Application Programing Interface(API)**
 
 **2. Destructing Data**
 
**3. Project**

**4. Modules**

**5. Debugging**

## ✨️ First: API
**APIs: are services that are exposing a whole bunch of data at a certain UPLs**
**JSON: JavaScript Object Notation**
### 📝 Notes:
1. Fetch() let us use JS to load data from APIs and it return promise object
2. Promise object represents the eventual completion (or failure) of an asynchronous operation and its resulting value.
   1. Three value for promise that return from fetch
      * Pending: still waiting for a value 
      * Fulfilled: aka resolved finally get the value all done 
      * Rejected: sorry could not get the value all done
3. Sometimes we want to wait for fetching data and then complete running the code, in this case we can use await keyword.
4. We can use await keyword only in a function that declare as async function, or if we want to use it in the top of code, I must make the type of js is module, the way will explain in modules
8. I can use json() method with data that we get from fetch to parse the data to a json object, this method will return a promise so I can use await with it.
9. JS can only do one task at a time (“single-threaded”) 

### Code Example:
```
const fetchData =async url=>{
    let response= await fetch(url)
    let data= await response.json();
    return data
}
```


## ✨️ Second: Destructing Data
**Destruction: is fancy way of declaring multiple variable at once by extracting values from an object with their property name**

### 📝 Notes:
1. By using destructing we can ignore the value in the array we do not need, we can use commas to skip values 
2. We can use the spread operator(…) the collect remaining value 

### Code Example:
```
let personAttribute= ["Ahmad", 20, "Palestine", "Ein Sara"]
let [fname, age]= personAttribute //It iis not necessary to make a variable from all attribute of the array
let [,,country]= personAttribute // skip attribute by using commas
let [fname1, ...info]= personAttribute //age, country, address will be the attributes of the info array
console.log (info);
console.log(`${fname}, ${age}, ${country}, ${fname1} ` );

//output: [ 20, 'Palestine', 'Ein Sara' ]
//        Ahmad, 20, Palestine, Ahmad
```
## ✨️ Third: Project: Doggo Fetch 
```
<!DOCTYPE html>
<!-- saved from url=(0067)https://anjana.dev/javascript-first-steps/3-doggofetch-starter.html -->
<html lang="en-US">

<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">

    <title>Doggo Fetch</title>
    <style>
        body {
            margin: 1rem auto;
            padding: 3rem;
            font-family: sans-serif;
        }

        header {
            width: 70%;
            margin: 1em auto;
        }

        main {
            max-width: 70%;
            margin: 0px auto;
            display: flex;
            flex-direction: column;
        }

        img {
            max-width: 100%;
        }

        #image-frame {
            font-size: x-large;
            text-align: center;
            margin: 1rem auto;
        }

        #explanation,
        #score {
            padding: 1rem;
            text-align: center;
        }

        #options {
            max-width: 100%;
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

        .hidden {
            display: none;
        }
    </style>
</head>

<body>
    <header>
        <h1>Guess the Doggo</h1>
        <p>What breed is the dog in this image?</p>

    </header>

    <main>
        <div id="image-frame">
        </div>
        <div id="options">
        </div>

    </main>




    <script type="module">

        const RANDOM_IMG_ENDPOINT = "https://dog.ceo/api/breeds/image/random";

        const BREEDS = ["affenpinscher", "african", "airedale", "akita", "appenzeller", "shepherd australian", "basenji", "beagle", "bluetick", "borzoi", "bouvier", "boxer", "brabancon", "briard", "norwegian buhund", "boston bulldog", "english bulldog", "french bulldog", "staffordshire bullterrier", "australian cattledog", "chihuahua", "chow", "clumber", "cockapoo", "border collie", "coonhound", "cardigan corgi", "cotondetulear", "dachshund", "dalmatian", "great dane", "scottish deerhound", "dhole", "dingo", "doberman", "norwegian elkhound", "entlebucher", "eskimo", "lapphund finnish", "bichon frise", "germanshepherd", "italian greyhound", "groenendael", "havanese", "afghan hound", "basset hound", "blood hound", "english hound", "ibizan hound", "plott hound", "walker hound", "husky", "keeshond", "kelpie", "komondor", "kuvasz", "labradoodle", "labrador", "leonberg", "lhasa", "malamute", "malinois", "maltese", "bull mastiff", "english mastiff", "tibetan mastiff", "mexicanhairless", "mix", "bernese mountain", "swiss mountain", "newfoundland", "otterhound", "caucasian ovcharka", "papillon", "pekinese", "pembroke", "miniature pinscher", "pitbull", "german pointer", "germanlonghair pointer", "pomeranian", "medium poodle", "miniature poodle", "standard poodle", "toy poodle", "pug", "puggle", "pyrenees", "redbone", "chesapeake retriever", "curly retriever", "flatcoated retriever", "golden retriever", "rhodesian ridgeback", "rottweiler", "saluki", "samoyed", "schipperke", "giant schnauzer", "miniature schnauzer", "english setter", "gordon setter", "irish setter", "sharpei", "english sheepdog", "shetland sheepdog", "shiba", "shihtzu", "blenheim spaniel", "brittany spaniel", "cocker spaniel", "irish spaniel", "japanese spaniel", "sussex spaniel", "welsh spaniel", "english springer", "stbernard", "american terrier", "australian terrier", "bedlington terrier", "border terrier", "cairn terrier", "dandie terrier", "fox terrier", "irish terrier", "kerryblue terrier", "lakeland terrier", "norfolk terrier", "norwich terrier", "patterdale terrier", "russell terrier", "scottish terrier", "sealyham terrier", "silky terrier", "tibetan terrier", "toy terrier", "welsh terrier", "westhighland terrier", "wheaten terrier", "yorkshire terrier", "tervuren", "vizsla", "spanish waterdog", "weimaraner", "whippet", "irish wolfhound"];


        // Utility function to get a randomly selected item from an array
        function getRandomElement(array) {
            const i = Math.floor(Math.random() * array.length);
            return array[i];
        }

        // Utility function to shuffle the order of items in an array in-place
        function shuffleArray(array) {
            return array.sort((a, b) => Math.random() - 0.5);
        }



        // TODO 1
        // Given an array of possible answers, a correct answer value, and a number of choices to get,
        // return a list of that many choices, including the correct answer and others from the array
        function getMultipleChoices(n, correctAnswer, possibleChoices) {
            // Use a while loop and the getRandomElement() function
            // Make sure there are no duplicates in the array
            const choices = [];
            choices.push(correctAnswer);
            while (choices.length < n) {
                let possibleChoice = getRandomElement(possibleChoices)
                if (!choices.includes(possibleChoice)) {
                    choices.push(possibleChoice);
                }
            }
            return choices
        }


        // TODO 2
        // Given a URL such as "https://images.dog.ceo/breeds/poodle-standard/n02113799_2280.jpg"
        // return the breed name string as formatted in the breed list, e.g. "standard poodle"
        function getBreedFromURL(url) {
            // The string method .split(char) may come in handy
            // Try to use destructuring as much as you can
            let fifthElement = url.split('/')[4];
            let [standard, poodle] = fifthElement.split('-');
            return [poodle, standard].join(" ").trim();

        }



        // TODO 3
        // Given a URL, fetch the resource at that URL, 
        // then parse the response as a JSON object,
        // finally return the "message" property of its body
        async function fetchMessage(url) {
            let response = await fetch(url)
            let data = await response.json();
            let { message } = data;
            return message;

        }


        // Function to add the multiple-choice buttons to the page
        function renderButtons(choicesArray, correctAnswer) {

            // Event handler function to compare the clicked button's value to correctAnswer
            // and add "correct"/"incorrect" classes to the buttons as appropriate
            function buttonHandler(e) {
                if (e.target.value === correctAnswer) {
                    e.target.classList.add("correct");
                } else {
                    e.target.classList.add("incorrect");
                    document.querySelector(`button[value="${correctAnswer}"]`).classList.add("correct");
                }
            }

            const options = document.getElementById("options"); // Container for the multiple-choice buttons

            // TODO 4
            // For each of the choices in choicesArray,
            // Create a button element whose name, value, and textContent properties are the value of that choice,
            // attach a "click" event listener with the buttonHandler function,
            // and append the button as a child of the options element
            for (let choice of choicesArray) {
                let button = document.createElement("button");
                button.textContent = choice;
                button.value = choice;
                button.name = choice;
                button.addEventListener('click', buttonHandler)
                options.appendChild(button)
            }

        }


        // Function to add the quiz content to the page
        function renderQuiz(imgUrl, correctAnswer, choices) {
            const image = document.createElement("img");
            image.setAttribute("src", imgUrl);
            const frame = document.getElementById("image-frame");

            image.addEventListener("load", () => {
                // Wait until the image has finished loading before trying to add elements to the page
                frame.replaceChildren(image);
                renderButtons(choices, correctAnswer);
            })

        }

        // Function to load the data needed to display the quiz
        async function loadQuizData() {
            document.getElementById("image-frame").textContent = "Fetching doggo...";

            const doggoImgUrl = await fetchMessage(RANDOM_IMG_ENDPOINT);
            const correctBreed = getBreedFromURL(doggoImgUrl);
            const breedChoices = getMultipleChoices(3, correctBreed, BREEDS);

            return [doggoImgUrl, correctBreed, breedChoices];
        }

        // TODO 5
        // Asynchronously call the loadQuizData() function,     
        // Then call renderQuiz() with the returned imageUrl, correctAnswer, and choices 
        try {
            const [imgUrl, correctAnswer, choices] = await loadQuizData();
            renderQuiz(imgUrl, correctAnswer, choices)
        } catch (error) {
            let err=document.createElement('p');
            err.textContent="Error has happened";
        }
        
      
    </script>

</body>

</html>
```
## ✨️ Forth: Module
**Modules: let us split big codebases across multiple file**
### 📝 Notes:
 1. To convert the type of js into module I can make json file and in it I can write ```{"type": "module"}```
 2. When I use module the scope will have some changes
 3. Module script make us use import and export

## ✨️ Fifth: Debugging
### 📝 Notes:
1. Ways to understand what happening when your program runs :
  * console.log ()
  * .warn()
  * .error()
2. You can use the browser's debugger to pause JS and inspect what's happening ```debuggers;```
  * The debugger statement ctreats a breakpoin where JS will pause and let you look around  
3. We can use try catch block with the code that we expected to throw an error 


# 💪 Challenge Solutions:
**[The assignment](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week1-day5-task/task.md)**

**[My solution ](https://github.com/Safa-Kamal-q/projects-ExpressJS-training/tree/master/characterProject)**


