---
title: What a game of Hangman can teach us about Node.js.
date: {{ date }}
---
<p style='line-height: 26px; font-size: 18px;'>Welcome to the wonderful world of Node.js! The example I am going to use is based on a 'Hangman' game written completely in Node.js. I chose this example because it uses a lot of Node concepts and allows the reader to see a 'real-life' example of server-side Javascript in action. [View Github Repo](https://github.com/dacogemini/hangman_node_version)

The first concept I'll cover is how to work with inputs in Node.js. There are a number of ways to work with inputs in Node.js. One way is to use the readline module. </p>

> Let's break down the first part of the code in our *index.js* file:

```
const readline = require('readline');
const rl = readline.createInterface({ 
    input: process.stdin, 
    output: process.stdout 
});```
<p style='line-height: 26px; font-size: 18px;'>
```javascript
// Require readline
const readline = require('readline');

// Create our readline interface 
const rl = readline.createInterface({                 
    input: process.stdin, 
    output: process.stdout 
});
```

<p style='line-height: 26px; font-size: 18px;'>Ok so far, so good. Now here is where things git a bit tricky. When learning programming concepts it's easy to get side-tracked, but I promise once we go down this 'rabbit-hole' we will get back to reading and processing input in a simpler fashion.

Notice that in our readline instance, we make use of another module, <em>the process module</em>.</p>

    input: process.stdin, 
    output: process.stdout 

<p style='line-height: 26px; font-size: 18px;'>We know that single threaded operations make Node.js processes more efficient and faster. We also know that most servers have multiple processors. We can easily leverage the extra processors to run our code in parallel with each other and the main application. Node.js offers three specific modules to help with this.
</p>

#### <em>process</em> Module
#### The <em>child_process</em> Module
#### The <em>cluster</em> Module </P>
--- 
## THE PROCESS MODULE
<p style='line-height: 26px; font-size: 18px;'> 
<strong>The process module provides access to the running processes.</strong> The child_process module provides the ability to create child processes and communicate with them. And cluster module implements clustered servers that share the same port, thus allowing multiple requests to be handled simultaneously. 

For our purposes, we will concentrate on <em>processes</em>, but before we do, let's take a moment and discuss <em>event emitters</em>.

Node.js has a built-in <strong>Event System</strong> that will allow us to emit and listen for events that occur.
Within this system is a standard module called <em>events</em> which includes an <em>EventEmitter Object</em> that allows us to manipulate events that occur. 

It's important to understand that the <em>process object</em> is an instance of <em>EventEmitter</em> and <em>stdin</em> & <em>stdout</em>
are process properties that allow us better control over system interactions. 

So, our <em>readline</em> (including our EventEmitter in the form of <em>process</em> module) is set and now we can tack on a listerer to listen to events (or running processes).

What is an example of a <em>running process</em> in our hangman game?
Well, anything that the user types in would be an example of a running process. 

Let's have a look at the options for our users.

1. If the user guesses a letter incorrently the following happens:

``` javascript
else if (guesses.indexOf(entry) == -1) // guessed word is -1 (meaning it is not in the array)...
    {
        guesses.push(entry);
        guessString += entry + " "; // guessString = guessString + entry
        if (word.checkGuess(entry) == false)
        {
            console.log("Incorrect, please try again!");
            chances--;
            console.log(`You have ${chances} chances remaining.`);
        }
    }
```

</p>

<!-- ![pipes in Node.js](../../source/img/pipe.gif) -->

## THE EVENT LOOP
<p style='line-height: 26px; font-size: 18px;'> 
Once the <em>readline</em> interface instance is created, the most common case is to listen for the 'line' event:
We do exactly this on line 32 in our Github repo </p>
``` javascript
rl.on("line", (input) => { 
    var entry = input.toUpperCase(); 
        if (entry == "QUIT" || entry == "NO") { 
rl.close(); 
}
// Note: our program will not exit until close() is called 
```
<p style='line-height: 26px; font-size: 18px;'> 
Line Event:
The 'line' envent is emitted whenever the in stream receives a \n , usually received when the user hits enter, or return.

<em>If you would like to know more about the readline module, stay-tuned. I am working on a blog post in which I show you how to make a 'Polish Notation' calculator with the readline module.</em></p>