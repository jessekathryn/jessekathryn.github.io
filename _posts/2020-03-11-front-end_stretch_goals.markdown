---
layout: post
title:      "Front-end Stretch Goals"
date:       2020-03-12 03:58:28 +0000
permalink:  front-end_stretch_goals
---


For my SAP JS Project, it was important to try out the fun JS enables for our web based experience.

In my Ruby project, CattleLog, I created my frontend design through incorporating BootStrap in my ERB files by importing via SCSS file.  If you are interested in doing this, here's a quick guide on YouTube, which is super easy to follow:

https://m.youtube.com/watch?v=Nf_Si8_szmM


In my last project, I had a pretty frontend, but it was not interactive with the user. A goal coming into this project was to fully engage JavaScipt with a page that could be added as a feature to my Rails app.  

Google API is truly a great resource to play with maps and get an understanding of how OOJS can work and simplify your JS code.

CattlelogFields is an extension of the CattleLog app.  It is an API featuring a front-end that will allow what more advanced farming software allows; drawing and layering over real life fields (or those which the farmer is actually taking care of).  Getting the API to work with the map was not difficult, because I figured out in my Ruby Project how to embed the app with dynamic coordinates.  This was extremely fun to do and not difficult through practice!

For this BS theme, I took the album theme from BS website here:
https://getbootstrap.com/docs/4.4/examples/album/

![](https://i.imgur.com/7tfVUXD.png)

I edited this theme to look like this and match my previous app's scheme:

![](https://i.imgur.com/AT2Stvc.jpg?1)

It takes time to play around and get used to moving objects, or in this case lines of JS, CSS, and HTML, on the backend to design the frontend. After practice, it becomes natural and you're going to love it, trust me.

If you want to try to use a Bootstrap theme for your JS project, definitely test it out. Find a them and start on the quick start page.  Just get the page up and running.  Make sure you add the css stylesheet link that matches to your css style sheet's title.  My stylesheet is 'style.css'.

This is what my header looks like order to engage the theme-->
```
<head>
    <script src="adapter.js" charset="utf-8"></script>
    <script src="field.js" charset="utf-8"></script>
    <script src="app.js" charset="utf-8"></script>
    <script src="index.js" charset="utf-8"></script>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no" />
    <meta http-equiv="x-ua-compatible" content="ie=edge" />

    <!-- Bootstrap core CSS -->
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css"
        integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh" crossorigin="anonymous">
    <!-- Custom styles for this template -->
    <link href="style.css" rel="stylesheet" />
</head>
```

Put this in the Custom styles for this template link--->

```
   <link href="style.css" rel="stylesheet" />
```

Create a CSS file matching the link above and make sure to link your CSS to your index.html file.  In this case, mine is titled "style.css".  
Inside your CSS file, copy and grab the CSS from the link provided on the BS example link on the 'View Page Source'.

![](https://i.imgur.com/5vk6fZT.png?1)

You can also change this CSS to your liking (colors, padding, customize!). There are so many and at first you feel limited, but there is a component for everything on this website (border, shadow, colors, carousel), read through it!

After you add different components to the index.html, you need to close your body tag with the JS links. 
```
       <!-- jQuery first, then Bootstrap JS. -->
        <script src="https://code.jquery.com/jquery-3.4.1.slim.min.js"
            integrity="sha384-J6qa4849blE2+poT4WnyKhv5vZF5SrPo0iEjwBvKU7imGFAV0wwj1yYfoRSJoZ+n"
            crossorigin="anonymous"></script>
        <script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js"
            integrity="sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo"
            crossorigin="anonymous"></script>
        <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js"
            integrity="sha384-wfSDF2E50Y2D1uUdj0O3uMBJnjuUD4Ih7YwaYd1iqfktj0Uod8GCExl3Og8ifwB6"
            crossorigin="anonymous"></script>
						
</body>
<html>
```

Congrats! You have a beautiful website that is also functioning as an API (in this project's case!) on the backend.  
 
 
 
 



