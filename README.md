---
layout: default
permalink: /
---

# Portfolio

![](/assets/headshot.jpg)

# [Resume](/resume.pdf)

<hr>

## Experience
<hr>

{% for post in site.posts %}
<p>
  <a href="{{ post.url }}">
    {% if post.splash %}
    <img src="{{ post.splash }}" height=200 style="object-fit:contain;">
    {% endif %}
    <figcaption>{{ post.title }}</figcaption>
  </a><br>
  {% if post.summary %}
  {{post.summary}}
  {% endif %}
</p>
<hr>
{% endfor %}

I am currently a student in the Master of Robotics Systems Development (MRSD) program at Carnegie Mellon University.

From 2022-2024, I was a member of Terps Racing Baja, competing to make the fastest and most durable ATV in the national Baja SAE collegiate competition. I have applied CAD, hand-written simulations, and physical testing to design high-quality parts and assemblies for the vehicle. From 2023-2024, I held the position of  Powertrain Subteam Leader. I supervised the design and implementation of the powertrain subsystem by planning, budgeting, and scheduling individual student projects. Under my leadership, we improved the car's acceleration time from 6s to 4.4s, with an overall placement in the top 25 of 100 teams during the 2024 competition season.

A hobby of mine for many years has been programming, especially for video game development. This passion and curiosity led to knowledge in topics beyond mechanical engineering, such as algorithms, data structures, and simulation. I further developed my programming and systems integration skills through a Robotics and Autonomous Systems minor at UMD and research at NIST's Digital Twin Lab. I am always looking for ways to combine my experience in computer programming with engineering to be a more effective problem solver.