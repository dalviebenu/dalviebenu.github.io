---
layout: page
title:  "Ethical Hacking Tool"
permalink: /ethical-hacking-tool/
---

# Ethical Hacking Tool

## What is Ethical Hacking Tool?
The ethical hacking tool (refered internally as the flask app) was a tool that I design to ease the workload on teaching assistants in the
ethical hacking course at KTH Royal Institute of Technology (where I did my bachelors).

The course was mainly practical, specifically, the course took the form of a capture the flag (CTF) competition. The students were given a set of
credentials and a simulation of a company's network. The students were then tasked with finding vulnerabilities in the network and exploiting them
to gain token. The tokens would be submitted and the more tokens a student gets, the higher their grade. However, their were hundreds of students
participating in the course and hence their were many instances of this corportate network (called worlds) hosted on the cloud. Whenever, an host in a particular
world would go down, the students would reach out and ask for a restart of the host or world. The teaching assistants would then use an internally
developed CLI tool to conduct this restart. It was found that most of the work down by the teaching assistants was to restart the worlds and hence it was
decided to create a tool that would allow the students to restart the worlds themselves.

## How does it work?
The flask app was a simple web application that developed in python using the flask framework (hence the name). It was deployed on the cloud using docker and
kubernetes. The app would ask the students to upload their credentials (public encryption key signed by our CA file) and then it would use the internal CLI tool
to conduct this restart (which is hosted on its own docker container). The app would then send a message back to the student about the state of their world.
The app would also limit the number of restarts per person and track all the restarts conducted by the students (using a local sqlite database).

![login](images/upload.png)
