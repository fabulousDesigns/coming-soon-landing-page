### Introduction

---

A Coming Soon landing page is a temporary home page that informs visitors that your website is in the process of being built or will be available soon.
Since a coming soon page lacks a header or a footer, visitors cannot navigate to the rest of your website hence it is important to capture what is under development so as to give as much information as possible.
Every coming soon page includes a statement encouraging visitors to return at a later time, as well as any other pertinent information concerning the website that is under development.
This article will teach you how to make a coming soon landing page but first things first you will learn about Javascript Timers to get you started.

#### Table Of Contents

---

- [introduction](#introduction)
- [Javascript Timers overview](#javascript-timers-overview)
- [code execution after a delay](#code-execution-after-a-delay)
- [Code Execution at Regular Intervals](#code-execution-at-regular-intervals)
- [Cancelling A Timer](#cancelling-a-timer)
- [Template section](#template-section)
- [Best practices](#best-practices)
- [conclusion](#conclusion)

### Javascript Timers Overview

---

A timer is a feature that allows us to run a program at a predetermined time.
Timers can be used to postpone code execution so that it doesn't finish at the same time as an event or a page loading.
Timers, for example, can be used to alter your website's advertisement banners at regular intervals or to display a real-time clock, among other things. In JavaScript, there are two timer functions: `setTimeout ()` and `setInterval ()`. Browsers implement timer functions, and their implementations differ from one browser to another. The Node.js runtime also has a native implementation of timers. In browsers, the window interface is the parent of the main timer features. setTimeout can be used in the browser console since the window interface makes its elements available globally in the main javascript scope.
'Timers' is an object in NodeJs that functions like the browser's window interface.

### Code Execution After a Delay

---

The `setTimeout()` function is used to only run a function or a piece of code once after a given amount of time has passed.

**syntanx**

`setTimeout(function, milliseconds)`.

You must give two parameters to utilize this function:A Function parameter that describes the function to be executed, and an optional Delay parameter that determines how long to wait before the function is executed (1 second = 1000 milliseconds).

**Example**

```javascript
<script>
function delayGreetings() {
    alert('Hello World!');
}
</script>
<button type="button" onclick="setTimeout(delayGreetings,2000)">click Me</button>
```

**when the button is clicked the greetings will be displayed after 2 seconds**

**NOTE :** If the delay parameter is 0 or if it is not specified, the function is executed immediately.

_TASK-1_

Use `setTimeout` function to print the following two messages after their respective delays .

- After 4 seconds, display greetings "Hello FabulousDesigns after 4secs"
- After 8 seconds, display greetings "Hello FabulousDesigns after 8secs."

  **CONSTRAIT :**
  In your solution, you can only define one function, which includes inline functions. As a result, a lot of setTimeout calls will have to use the same code.

  **SOLUTION**

  - **Task-1** may be solved in a variety of ways, but this is one of them.

  ```javascript
  const delayGreetings = (delay) => {
    console.log("Hello FabulousDesigns after " + delay + " seconds");
  };
  setTimeout(delayGreetings, 4 * 1000, 4);
  setTimeout(delayGreetings, 8 * 1000, 8);
  ```

#### Explanation

- I gave delayGreetings a delay parameter and utilized the delay argument's value in the displayed message. As a result, depending on the delay value we provide to the function, it might print different messages.

- After that, I used delayGreetings function in two setTimeout calls, one for 4 seconds and the other for 8 seconds. A third parameter is sent to both of these setTimeout calls to represent the delay argument for delayGreetings.

### Code Execution At Regular Intervals

---

Similarly, the setInterval() method may be used to execute a function or a given piece of code at certain intervals.

**syntanx**

`setInterval(function, milliseconds)`.

To begin with,the first parameter is the actual function to execute,and the second parameter is the interval which represents amount of time to wait before executing the function (1 second = 1000 milliseconds).
**Example**

```javascript
setInterval(
  () => console.log("Hello fabulousDesigns after every 3 seconds"),
  3000
);
```

The above code executes after every 3 seconds.

_Task-2_

- use setInterval function to display your local computer time after every one second.

  **Solution**

- one of the way to sovle **Task-2** is:

```javascript
<script>
function displayTime() {
    var d = new Date();
    document.querySelector("#clock").innerHTML = d.toLocaleTimeString();
}
setInterval(displayTime, 1000);
</script>

<p>current time on your computer is: <span id="clock"></span></p>
```

After every 1 second, the showTime() method is executed. It Retrieves your computer's current time and shows it in your browser each time it executes.

### Cancelling A Timer

---

Using the setTimeout() and setInterval() methods will return an integer value that will identify the timer generated by these methods by its unique ID.
You may deactivate or clear the timer with this ID and stop the execution of code in advance by using this ID to disable or clear it. Two methods are available for clearing a timer: clearTimeout() and clearInterval ().
To clear a setTimeout() timer for a specific Id, use this function, as seen in the following example:

```javascript
<script>
var timeoutID;

function delayedAlert() {
  timeoutID = setTimeout(displayGreetings, 2000);
}

function displayGreetings() {
  console.log('Hello fabulousDesigns.');
}

function clearGreetings() {
  clearTimeout(timeoutID);
}
</script>

<button type="button" onclick="delayedAlert();">Show greetings After Two Seconds</button>

<button type="button" onclick="clearAlert();">Cancel greetings Before It is Display</button>

```

- It is also possible to remove or disable a setInterval() timer using the clearInterval() function.

```javascript
<script>
var intervalID;

function showTime() {
    var d = new Date();
    document.getElementById("clock").innerHTML = d.toLocaleTimeString();
}

function stopClock() {
    clearInterval(intervalID);
}

var intervalID = setInterval(showTime, 1000);
</script>

<p>The current time on your computer is: <span id="clock"></span></p>

<button onclick="stopClock();">Stop Clock</button>
```

**Note:** ClearTimeout() and clearInterval() can be used interchangeably. You should avoid this, though, for the sake of clarity and code maintainability.

### Here are five pointers for developing a successful coming soon landing page.

---

#### 1. Make an impact without being overbearing.

Focus on the headline and a short description. Both should concentrate on what you're offering and how it will improve your customers' lives.

As an example:

In the described template, the headline "THE REAL SOUND" evokes the appropriate emotions.

Visitors to this website will at least have an idea of what to expect based on the headline, which is downloading and listening to HD hits.

#### 2. You'll only have to fill out one form.

A typical landing page can have up to two or three sign up pages, however a coming soon landing page can only have one. It's critical that you just focus on customers' eyes on a coming soon landing page because the more users you get to join and sign up, the more likely you are to lose them.

In the Example template below, you can add a modal form to the getNotified button so that when constomers click it, a modal form appears, allowing them to sign up and be alerted.

#### 3. Set a countdown

Setting a countdown is one approach to significantly boost the conversion rate of your coming soon page.A physical, adjustable countdown clock can be used to do this.
If you don't have a specific launch date in mind, you might say something like "arriving this fall" or "out in time for Christmas."

#### 4. Make it shareable

Create a giveaway to increase the number of social shares your landing page receives across important platforms. Customers can enter this giveaway by sharing it on Facebook, retweeting it on Twitter, or posting about it on Instagram.

#### 5. Make it mobile

This emphasizes that the page should be responsive, implying that all functionality should be the same regardless of whether the user is on a computer, an iPad, or a mobile phone.

### Template Section

---

In this section, i have designed a responsive landing page.I have used some bootstrap to sought of achive page resposiveness.Feel free to edit the code to make more better.

![large-devices](temp01.png)
![medium-devices](temp02.png)
![small-devices](temp003.png)

#### source code

**MARK UP SECTION**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Coming Soon Landing Page</title>
    <link rel="stylesheet" href="css/bootstrap.min.css" />
    <link rel="stylesheet" href="css/style.css" />
  </head>
  <body>
    <header>
      <div class="container">
        <div class="row">
          <div class="col-md-4">
            <h1 class="display-1 text-center">
              THE <br />
              REAL <br />
              SOUND
            </h1>
            <p class="lead text-center">
              listen to hd music and download for free.
            </p>
            <img
              src="img/tw.png"
              alt="twitter"
              class="m-3"
              width="40px"
              style="border-radius: 20px; cursor: pointer;"
            />
            <img
              src="img/fb.png"
              alt="Facebook"
              class="m-3"
              width="40px"
              style="border-radius: 20px; cursor: pointer;"
            />
            <img
              src="img/gp.png"
              alt="google"
              class="m-3"
              width="40px"
              style="border-radius: 20px; cursor: pointer;"
            />
            <button type="button" class="btn btn-primary">getNotified</button>
          </div>
          <div class="col-md-8 mt-3" style="display: flex;align-items:center;">
            <div
              class="card m-3"
              style="width: 350px; background-color: #20201f; cursor: pointer;"
            >
              <img
                src="img/album01.jpg"
                alt="album01"
                width="350"
                class="card-img-top"
              />
              <div class="card-body">
                <h5 class="card-title">ALBUM 01</h5>
                <p class="card-text">Lorem ipsum dolor sit amet consectetur</p>
                <a href="#" class="btn btn-primary d-block">Listen Now</a>
              </div>
            </div>
            <div
              class="card"
              style="width: 350px; background-color: #20201f; cursor: pointer;"
            >
              <img
                src="img/album01.jpg"
                alt="album02"
                width="350"
                class="card-img-top"
              />
              <div class="card-body">
                <h5 class="card-title">ALBUM 02</h5>
                <p class="card-text">Lorem ipsum dolor sit amet consectetur</p>
                <a href="#" class="btn btn-primary d-block">Listen Now</a>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="container">
        <div class="row">
          <div class="col-md-12">
            <p class="lead text-center">Support My Music</p>
            <h4 class="display-4 text-center" style="letter-spacing: 12px;">
              COMING SOON
            </h4>
            <hr />
            <p id="launch" class="lead"></p>
          </div>
        </div>
      </div>
    </header>

    <script src="js/main.js"></script>
  </body>
</html>
```

**CSS SECTION**

```css
header {
  background-image: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)),
    url(../img/background.jpg);
  height: 100vh;
  background-position: center;
  background-size: cover;
  color: #fff;
}
.card img {
  border-radius: 30% 70% 0% 100% / 0% 0% 100% 100%;
}
hr {
  width: 50%;
  margin: 30px auto;
  border: #f0f0ea solid 1.5px;
}
#launch {
  text-align: center;
  font-size: 40px;
}
```

**JAVSCRIPT SECTION**

```javascript
let countDownDate = new Date("sep 1,2021 00:00:00").getTime();

let x = setInterval(() => {
  let now = new Date().getTime();

  let distance = countDownDate - now;

  let days = Math.floor(distance / (1000 * 60 * 60 * 24));
  let hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
  let minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
  let seconds = Math.floor((distance % (1000 * 60)) / 1000);

  document.querySelector("#launch").innerHTML =
    days + " d " + hours + " h " + minutes + " m " + seconds + " s ";

  if (distance < 0) {
    clearInterval(x);
    document.querySelector("#launch").innerHTML = "EXPIRED";
  }
}, 1000);
```

- Here's a link to the github repository where you can see the source code.

- [view source code at github](https://github.com/EssyG10/coming-soon-landing-page.git)

### Conclusion

---

Because JavaScript engines only have one thread, asynchronous events are forced to wait in a queue for execution.
The way setTimeout and setInterval run asynchronous code is fundamentally different.
All of this information is highly essential and paramount.Knowing how a JavaScript engine works is a wonderful basis for constructing complex application code, especially given the enormous amount of asynchronous events that normally occur.

Building a user attractive coming soon landing page will boost the rate of attracting users to register in your site always go for user sight.
To do so, make sure your landing page is responsive, include a countdown, and include your social media links. Also, make sure your website is capable of notifying people so that they may subscribe with their email addresses to be notified when the page is ready to be launched.

#### Further Reading

---

- Timers Implementation in NodeJs

Happy Coding!
