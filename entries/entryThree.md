# Building a Web Chat

## Intro
Now that I am familiar with Javascript and some Firebase code, it's time to start building an app from a [Firebase Web Codelab](https://codelabs.developers.google.com/codelabs/firebase-web/#0). This app is essentially just a web chat that interacts with the database to allow users to send messages to each other. It uses authentication and enables the user to send photos to each other. **I will not be going over the tutorial, rather I will point out the struggles I went through**. This is me showing how to google efficiently.

## Overview

There was not really any issues with the code itself, it was mainly getting the code to be able to run on a local server and allowing the database to contact with the local server. A lot of googling was done to see how other people dealt with these same problems.

## Login Issues

First Issue that I came across was being able to verify/authenticate my identity. To be able to login through your gMail, you have to write ```firebase login``` however, whenever I wrote it in the command line it would give me a link where I could authenticate my identity which ended up just being a broken link that didn't take me anywhere. After a few tries I realized this had to be a common error. When I opened google in another tab I knew some keywords where going to be "firebase", "login", and "CLI" which stands for Command Line Interface. Right away the first link had the answer to my problem. The authentication will not go through because of the proxy server at use here. The answer to the issue was just ```firebase login  --no-localhost```. First problem solved using keywords from my errors.

## Outdated NPM

The second issue had to do with an outdated CLI. I had no idea what the error was except that I need a more update CLI. One of the errors that came up when I tried to run a server for my code was ```Node.js v6.11.5 or greater is required```. I literally copy and pasted that into google along with firebase at the end. The first link that came up was a thread of people attempting to solve the same problem. After doing a little reading I discovered how to install the correct version I needed. I had to find out the different NVM versions where available to me and then just simply ```nvm install v6.12.0``` and then ```npm -g install firebase-tools``` to make the commands accessible to the new NVM. Another successful google search.

**NVM** = Node Version Manager

**NPM** = Node Package Manager

## Server Issue

Lastly, before I was able to get my server up and running I had trouble starting it up. Luckily for me this is an issue with Cloud9 so finding a loophole around starting up a server wasn't that hard. I googled "firebase serve failed to load". Since this was a common issue with Cloud9 there a forum on this issue. The loophole around this is to just write ```firebase serve -p $PORT -o $IP``` instead of ```firebase serve```. Immediately I though about using shotgun to run our ruby files a month or two ago to run our app.

## Takeaways

Googling is good and all but only if you are able to use it well. **Key Terms** are the most helpful terms you can google along with error messages. Always edit your searches if the first search gave a little too broad of a spectrum for what you were hoping for.