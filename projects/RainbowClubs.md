---
layout: project
type: project
image: images/landing.jpg
title: RainbowClubs
permalink: projects/RainbowClubs
# All dates must be YYYY-MM-DD format!
date: 2019-01-16
labels:
  - Automatization
  - Java
  - Apache POI
summary: I automated the closing tasks at my current job, by pulling data from multiple excel documents using Apache POI
---

<div class="ui two column grid">

  <div class="ui column">
    <a href="../images/listclubs.png">
    <img class="ui massive image" src="../images/listclubs.png"/>
    </a>
  </div>
  
  <div class="ui column">
    <a href="../images/adminpage.png">
    <img class="ui massive image" src="../images/adminpage.png"/>
    </a>
  </div>
</div>

<h1>First project with webdev</h1>
This was my first project I ever accompolished collaboritively and in the realm of web development. There were a lot of learning pains going through it. At first everything seemed like a massive feat
then as I learned the tech stack a little better (Meteor and Semantic UI) everything seemed to go rather smoothly.

It was simply a website that allowed us to take the data from <a href="http://www.manoa.hawaii.edu/studentlife/studentorg/rio.php">UH Manoas registered independant organizations</a> and allow people to register/manage/browse the clubs.

<h1>Working with a team</h1>
One major hurdle in this project was learning to work with a team. All projects up until this point in my life I have been able to accomplish solo. This one was another beast all together. It required communication and relying on
other teammates to do their parts so that I could finish mine. There were at times where I had to hold off on commiting because another feature needed to be implemented or my update would have broken. So I had to wait for the teammate to finish theirs, merge the changes they made into my branch, then update accordingly. The fix would probably have been to assign things that relied on other things all to one person, but sometimes this couldn't be avoided.

<h1>Tech Stack</h1>
The tech stack that was chosen for this project was Meteor/Semantic UI React/ MongoDB. 

One of the biggest hurdles was learning Meteor. A lot of what it does seems like magic at first like utilizing Tracker and Subsciptions. Also, the documentation seemed a bit conflicting at times. In one place it said never to use profile, in another it gave a shining example of how to use it and just warned that you should not store sensitive data there. The way we utilized it in the base project we were given was a bit different too. All over stackoverflow people were using templates to get things done, we didn't. So it was a bit hard to research just how something should be done. 

Learning to do things the React way was another learning curve. React allows you to build reusable components that can update with new data without reloading. At first I didn't see how to do this easily, it didn't seem natural
to me coming from my primary language Java. Then it all fell into place after a few hours of reading the doc/practice. Learning how to manage state/props/and update dynamically made things so much easier.

MongoDB was the easiest part to learn. You simply connect Meteor to your MongoDB and anytime you create a new collection it will update the DB for you. It was honestly plug and play and the syntax was very easy to use.

<h1>Something that I spent hours on that I didn't have to</h1>
The major bug that I had came at the end. The project worked beautifully locally, but when I deployed it nothing worked. I was getting undefined for the user types that should have been saved in Meteors account collection. So I
went back to the docs and it said profile should not be used due to security concerns since it is automatically read/write allowed for the client. So I decided to rewrite it using a subscription. Still worked locally and deployed no go. So I used an app called <a href="https://robomongo.org">Robo 3T</a> to inspect the MongoDB (I could have used mini mongo but I wasn't too sure if it was actually connecting to the DB). I logged in and lo and behold the user accounts were there, but their profile data was empty. I poured over the code that created accounts and could see nothing wrong. Then it dawned on me, what if nothing was being passed? I opened up the settings.development file and looked at the user accounts json and it was fine. Then another realization, this is not the file that is used when I deploy. I open up the settings.production file and there it is. No type data in any of there default users json. So on creation, no data was being passed thus undefined.




Source: <a href="https://github.com/rainbowclubs/rainbowclubs"><i class="large github icon"></i>RainbowClubs</a>




