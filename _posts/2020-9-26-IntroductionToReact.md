---
layout: post
title: Introduction to Reat.js
---

In this article, I am going to introduce you to React.js and make a simple app with it. So, let`s go on

## What is React?


<div style="text-align:center" width="10" height="10">
<img src="assets/React-intro/reactlogo.svg" width=30%>
</div>


React is popular and famous framework to develop Front-End applications like Vue.js and Angular.js or as a reference to its website, "**A JavaScript library for building user interfaces**" . Originally, designed by facebook team released at May 29, 2013 and it is also used in many websites and apps like facebook, Dropbox, Airbnb, Netflix, Tesla, and ...

As it can be understood from its name, with React, you can develop highly reactive single-page or multi-page Front-End applications and its philosophy and purpose is to devide various simple components and merge them as a united app. Therefore, making applications in small components, could be one of the best approaches you can use for making these apps.

<div style="text-align:center" width="10" height="10">
<img src="assets/React-intro/react 01.png">
</div>

React is easy to understand and by more practices, you can aquire a good skill in it. So let`s dive deeper in it

## Start

Initially, to create our first react app, we use a secondary package designed by react team which is **create-react-app**. Of course our app can be made from scratch, we use this package as a highly easier method.
It can be found at both **npm**(Node Package Manager) and **yarn** and from now on, I will use the first one.

<div style="text-align:center" width="10" height="10">
<img src="assets/React-intro/react 02.png">
</div>

In order to have it on your system, an installed npm is required. Afterwards, you can simply install it with below command:

> npm i create-react-app

Now, by installing that, we can craete our first React app. So change your directory to your prefered one and open the console or prompt. Then, enter the command with below format:

>create-react-app YOURAPPNAME --script-version VERSION_NUMBER

You may leave **--script-version** section. By that, the latest version will be installed.

After this process has been completed, open that directory with your code editor or IDE. I will personally use VSCode.

<div style="text-align:center" width="10" height="10">
<img src="assets/React-intro/react 03.png">
</div>


Here is our first app, for running it, change directory to your app folder, then open terminal and write:

> npm start

And by the time I write this article, you will see below page:

<div style="text-align:center" width="10" height="10">
<img src="assets/React-intro/react 04.png">
</div>


A good point is that, by this command, you won't need to re-run this code every time your code changes. Actually, it will refresh automatically as it senses a change.

Here is my react app which I named it **first-app**. As you can see there's a ***package.json*** file which stores the prequisites and required packages for our app to run. What matters to us the most, are **src** and **public** folders which hold the main code we need.

Let`s review the code.

What we see initially, is **index.html** in **/public** folder. For my version, the code is like below:

``` html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <link rel="icon" href="%PUBLIC_URL%/favicon.ico" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <meta name="theme-color" content="#000000" />
    <meta
      name="description"
      content="Web site created using create-react-app"
    />
    <link rel="apple-touch-icon" href="%PUBLIC_URL%/logo192.png" />
    <!--
      manifest.json provides metadata used when your web app is installed on a
      user's mobile device or desktop. See https://developers.google.com/web/fundamentals/web-app-manifest/
    -->
    <link rel="manifest" href="%PUBLIC_URL%/manifest.json" />
    <!--
      Notice the use of %PUBLIC_URL% in the tags above.
      It will be replaced with the URL of the `public` folder during the build.
      Only files inside the `public` folder can be referenced from the HTML.

      Unlike "/favicon.ico" or "favicon.ico", "%PUBLIC_URL%/favicon.ico" will
      work correctly both with client-side routing and a non-root public URL.
      Learn how to configure a non-root public URL by running `npm run build`.
    -->
    <title>React App</title>
  </head>
  <body>
    <noscript>You need to enable JavaScript to run this app.</noscript>
    <div id="root"></div>
    <!--
      This HTML file is a template.
      If you open it directly in the browser, you will see an empty page.

      You can add webfonts, meta tags, or analytics to this file.
      The build step will place the bundled scripts into the <body> tag.

      To begin the development, run `npm start` or `yarn start`.
      To create a production bundle, use `npm run build` or `yarn build`.
    -->
  </body>
</html>

```
 
 As you see the last **div** tag, the **root** id is given. This div is a refrence to **index.js** file in **src** folder.


 ``` js
 import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
import App from './App';
import * as serviceWorker from './serviceWorker';

ReactDOM.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById('root')
);

// If you want your app to work offline and load faster, you can change
// unregister() to register() below. Note this comes with some pitfalls.
// Learn more about service workers: https://bit.ly/CRA-PWA
serviceWorker.unregister();

 ```

 At the end of this file, there is a ***document.getElementById('root')*** command, which links to the **div** tag in **index.html**.

 More on, there is another refrence in this code. If you see more precisly, a variable named **App**, is imported from this directory and used in here.
 Concisly, we are going to use that **App** from **App.js** most of the time and you saw a chain-like connection from **App.js** to **index.js** and finally to **index.html**.

 So we go directly to **App.js** :

 ```js
import React from 'react';
import logo from './logo.svg';
import './App.css';

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Edit <code>src/App.js</code> and save to reload.
        </p>
        <a
          className="App-link"
          href="https://reactjs.org"
          target="_blank"
          rel="noopener noreferrer"
        >
          Learn React
        </a>
      </header>
    </div>
  );
}

export default App;

 ```

 This is the main code we're working with. Let's read it line by line.
 Firstly, **React** library is imported. Then **logo** is just the image you can see on your app running. Additionally, a **css** file is inserted.

 Then we have a function called **App** and you can see, this file is exported which works like an output in which it is used it in **index.js**.

 Inside the function, we have a **return** command which actually returns a big block of code. What's in there??

 There's a **div** tag, **img** tag and so on. It looks quite like **html**, isn't it?

 SORRY, I have to disappoint you. Technically, it's not **html**. This block of code is called **jsx**, it's a syntactical sugar which looks like exactly like **html** with some extra powerfull feature which leads us to make really nice components!

 You can see there is an **img** tag which shows the rotating **log** on your browser.A **p** tag, that is on your screen and finally a **Learn React** statement.

 As you saw, this **App.js** is what we see on the browser which runs our application.

 By further articles, I will instruct you how to make your own React applications!.

 Thanks for reading.
