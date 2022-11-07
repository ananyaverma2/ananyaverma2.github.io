---
layout: default
title: Home
permalink: /home/
image: 01.jpg
---



<div class="hero">
  <div class="container">
    <div class="row">
      <div class="col-sm-8 last-item" >
        <div class="hero__content">
          <h1 class="hero__title" style="text-align:right">{{ site.data.settings.author.say-hello }}</h1>
          <div class="hero__social" style="margin-left:53%;">
            <span class="hero__social-title">Contact Me |</span>
            {% include contact-link.html %}
          </div>
        </div>
      </div>
      <div class="col-sm-4">
        <p style="text-align:center;"><img style="border:5px double black;" src="{{site.baseurl}}/images/{{ site.data.settings.author.image }}" alt=""></p>
      </div>
    </div>
    <p style="margin-left:30px; margin-top: 2cm;"> I am currently a Master student in Autonomous Systems at Bonn-Rhein-Sieg University of Applied Sciences in Bonn, Germany.</p>
    <h3 style="margin-left:30px;">Research Interests</h3>
    <p style="margin-left:30px;"> Robotics Developer with a penchant for Robot Perception robot. I like to work in Computer Vision and Robot Operating Systems (ROS) mostly coding in Python. In my free time, I like to read about Astrophysics and Space Exploration. Additionally, I have an incurable addiction to books.</p>
  </div>
</div>
