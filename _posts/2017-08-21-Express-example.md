---
layout: post
title: Example Express App
date: 2017-08-21 13:32:20 +0300
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: express.png # Add image post (optional)
tags: [Blog, Express, NodeJS]
author: # Add name author (optional)
---
# Express Routing Example Express

1. Creating a brand new express app from scratch
2. Create a package.json using `npm init` and add express as a dependency
3. In the main app.js file, adding 3 different routes:

Visiting "/" should print "Hi, there, welcome to this example"

===========================================================

Visiting "speak/pig should print "The pig says 'oink'"
Visiting "speak/cow should print "The pig says 'moo'"
Visiting "speak/dog should print "The pig says 'woof woof'"

===========================================================

Visiting "repeat/hello/3 should print "hello hello hello"
Visiting "repeat/hello/5 should print "hello hello hello hello hello"
Visiting "repeat/blah/3 should print "blah blah blah"

If a user visits any other route, print:
"Sorry, page not found... Fook is gone maybe, init, bruv!!"

```
var express = require("express");
var app = express();

app.get("/", function(req,res){
  res.send("Hi, there, welcome to this example!!");
  console.log("Someone has gone to the main page init!!");
})

app.get("/speak/:creature", function(req,res){
//   res.send("Creature says what?");
  var creatures = req.params.creature;

// logic
  // if creature is this print this
  if (creatures == "dog"){
    res.send("The "+ creatures +" says 'Woof Woof!'");
    console.log("The "+ creatures +" says 'Woof Woof!'");
  }
  else if (creatures == "cow"){
    res.send("The "+ creatures +" says 'Moo!'");
    console.log("The "+ creatures +" says 'Moo!'");
  }
  else if (creatures == "pig"){
    res.send("The "+ creatures +" says 'Oink!'");
    console.log("The "+ creatures +" says 'Oink!'");
  }
  else if (creatures == creatures){
    res.send("The "+ creatures +" says 'you!'");
    console.log("The "+ creatures +" says 'you!'");
  }
})

app.get("*", function(req, res){
  res.send("Sorry, page not found... Fook is gone maybe, init, bruv!!");
  console.log("Someone has gone to limbo init!!");
})

app.listen(3000, function(){
  console.log("server has started on port 3000");
})
```
