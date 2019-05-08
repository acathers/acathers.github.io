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

<h1>Working with a team</h1>
This was my far the biggest hurdle in this project. All projects up until this point in my life I have been able to accomplish solo. This one was another beast all together. It required communication and relying on
other teammates to do their parts so that I could finish mine.

<h1>Tech Stack</h1>
The tech stack that was chosen for this project was Meteor/Semantic UI React/ MongoDB. I'd say the biggest hurdle was learning Meteor. A lot of what it does seems like magic at first like utilizing Tracker and Subsciptions.

<h1>Things that I spent hours on that I didn't have to</h1>
The first major bug that I had came at the end. The project worked beautifully locally, but when I deployed it nothing worked. I was getting undefined for the user types that should have been saved in Meteors account collection. So I
went back to the docs and it said profile should not be used due to security concerns since it is automatically read/write allowed for the client. So I decided to rewrite it using a subscription. Still worked locally and deployed no go. So I used an app called <a href="https://robomongo.org">Robo 3T</a> to inspect the MongoDB (could have used mini mongo but I wasn't too sure if it was actually connecting). I logged in and lo and behold the user accounts were there, but their profile data was empty. I poured over the code that created accounts and could see nothing wrong. Then it dawned on me, what if nothing was being passed? I opened up the settings.development file and looked at the user accounts json and it was fine. Then another realization, this is not the file that is used when I deploy. I open up the settings.production file and there it is. No type data in any of there default users json. So on creation, no data was being passed thus undefined.




Source: <a href="https://github.com/acathers/ReportGenerator"><i class="large github icon"></i>ReportGenerator</a>




