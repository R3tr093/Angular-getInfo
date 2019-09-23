<img src="main.png">

# GetInfo

<p>hello there, welcome on this repository i'm gonna explain how to deploy an <b><i>MEAN API RESTful on Heroku.</b></i></p>

<p>The current repository is hosted on heroku, so you can find it on this address : <a href="https://hamilton19.herokuapp.com/" target="_blank" > hamilton19.herokuapp</a></p>

<p>If you are still interested i let you read the chapters below, and i hope you gonna find them helpfull.</p>

good reading !  :notebook:

<ul> <h4>Table of contents</h4>
    <li href="#c1"> Prerequisite </li>
    <li href="#c2"> Create a new App </li>
</ul>


<p> <b>Sources</b>  :point_down: </p>

<p><i><a href="https://devcenter.heroku.com/articles/mean-apps-restful-api" target="_blank"> Heroku </a></i></p>
<p><i><a href="https://www.codemeals.com/angular/deploy-angular-7-app-to-heroku/" target="_blank"> codeMeals</a></i></p>



<h2 id="c1"> Prerequisites </h2><hr>

<p>For a good beginning, i will let you know you probably should have some soft skills with MongoDB, Angular, And express.</p>

<p>If you don't have any knowledge about these things, you should practice a little bit with them.  :wink: </p>

<p> Well, the first thing we have to do is to ensure we get an recent version of node on our system.<br>
    For the entire article, i use an Linux Debian operating system, i let you search about the same command for your operating system as well.</p>

<p> We need a version of node higher at the  8.0.0, i wrote this application under node version 10.16.0, you can install node.js on the website below : </p>


<p><a href="https://nodejs.org/en/" target="_blank" > nodejs.org</a></p>

<p> Check if you nodejs installation is working by the command : <b><i>node -v </i></b> <br>You should also have npm installed you can check if is working also by the command : <b><i> npm -v </i></b>


<p> Now you need to get a verified account on Heroku, register yourself on <a href="https://signup.heroku.com/" target="_blank" > Heroku</a></p>

<p> For this tutorial we gonna use the Heroku CLI, you can download it on ubuntu by the command :<br> <b><i>sudo snap install --classic heroku</i></b>, find all informations you need about the Heroku CLI here : <a href="https://devcenter.heroku.com/articles/heroku-cli" target="_blank">https://devcenter.heroku.com/articles/heroku-cli</a></p>

<p> A last thing you need to get is the angular-CLI, you can use this command in your terminal to install angular/cli<br>
<b><i> npm install -g @angular/cli </i></b>

<p> Now let's code  :ok_hand: </p>


<h2 id="c2"> Create a new App </h2>

<p> With the angular/cli you can create a new project really quickly, use the command below to create a new angular project. </p>

<code> ng new myAppName </code>

<p><em> Feel free to replace myAppName by something more original </em></p>

<p> Now move into your new directory </p>

<code> cd myAppName </code>

<p>We need to use Express as a server for our application, install Express with the command below : </p>

<code>npm install --save express path</code>

<p><em>  :exclamation: Don't forget the flag <b>--save </b> </em></p>

<p>We gonna write some code to verify we have our angular application connected with Express, in first we need to create a file named server.js to write our source code for the server.</p>

<p>In the root of your project type the command below : </p>

<code>touch server.js</code>

<p>Into this nice empty file, write some code like this for the example.</p>

<code>const express = require('express'); </code>
<code>const path = require('path'); </code>
<code>const app = express(); </code>
<code>app.use(express.static(__dirname + '/dist/MY_APP_NAME_HERE'));</code>
<code>app.get('/*', function(req, res) {res.sendFile(path.join(__dirname + '/dist/MY_APP_NAME_HERE/index.html'));}); </code>
<code>app.listen(process.env.PORT || 3000); </code>
<p><em>  :exclamation: Don't forget to write your own app name</em></p>

<p>In your root directory you should have a file named package.json, edit this file by adding the following code : </p>

<p> At the end of the array named scripts : </p>

<code>"postinstall": "ng build --aot --prod" </code>

<p>Put inside or create an array "engines" with  your node version and npm version in your package.json file </p>
<code>"engines": {</code>
<code>  "node": "~8.15.1",</code>
<code>  "npm": "~6.4.1" }</code>