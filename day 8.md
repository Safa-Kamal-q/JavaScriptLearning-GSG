 <h1 align="center">🚀 Day 8 </h1>

 # course: [JavaScript: The Hard Parts, v2](https://frontendmasters.com/courses/javascript-hard-parts-v2/)

  # 🔎 Topics:
**1. Asynchronous**

**2. Web Browser**

**3.. Promise**

**4.  Microtask queue, Callback queue**

## ✨️ First: Asynchronous
**Asynchronicity: the feature that makes dynamic web applications possible**

**JavaScript is:**
  
    - Single threaded (one command runs at a time)
    
    - Synchronously executed (each line is run in order the code appears)

    - So what if we have code that takes a long time while excuting, and below it there is code that don't depende on it?

### 📝 Notes:
1. Generally JS is synchronous but also there is asynchronous method like setTimeOut also I can make any function run asynchronous, ex:
     ```
     function printHello(){
     console.log("Hello");
    }
    setTimeout(printHello,0);
    console.log("Me first!");
    //the output: Me first
    //Hello
     ```
2. JS run setTimeOut after run all the synchronous code below it even we write 0 ms

## ✨️ Second: Web browser
Web browser contain:
  1. JS engine
  2. some feature
     * Console=> console in JS
     * Network request=> fetch in JS
     * HTML DOM=> socument in JS
     * Timer=> setTimeOut in js 

## ✨️ Forth: Promise
**Promise: is special objects built into JavaScript that get returned immediately when we make a call to a web browser API/feature (e.g. fetch) that’s set up to return promises (not all are)**
### 📝 Notes:
1. One of the ES6 feature
2. Using two-pronged ‘facade’ functions that both:
    - Initiate background web browser work and
    - Return a placeholder object (promise) immediately in JavaScript
3.  Rules for the execution of our asynchronously delayed code
   * Hold promise-deferred functions in a microtask queue and callback function in a task queue (Callback queue) when the Web Browser Feature (API) finishes
   * Add the function to the Call stack (i.e. run the function) when:
        - Call stack is empty & all global code run (Have the Event Loop check this condition)
    * Prioritize functions in the microtask queue over the Callback queue
4. With promise object I can use .then(response callback function) and .catch(rejected callback function)

## ✨️ Third: Microtask queue, Callback queue
| Callback Queue | Microtask Queue |
| ----------- | ----------- |
| Callback Queue gets the ordinary callback functions coming from the setTimeout() API after the timer expires. | Microtask Queue gets the callback functions coming through Promises and Mutation Observer. |
| Callback Queue has lesser priority than Microtask Queue of fetching the callback functions to Event Loop. | Microtask Queue has higher priority than Callback Queue of fetching the callback functions to Event Loop. |



## ✨️📝 Note
**Promises, Web APIs, the Callback & Microtask Queues and Event loop enable:**
1. **Non-blocking applications:** This means we don’t have to wait in the single threadand don’t block further code from running
2. **However long it takes:** We cannot predict when our Browser feature’s work will finish so we let JS handle automatically running the function on its completion
3. **Web applications:** Asynchronous JavaScript is the backbone of the modern web-letting us build fast ‘non-blocking’ applications

# 💪 Challenge Solutions:
[Tap here to see the questions](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day3-tasks/tasks.md)


