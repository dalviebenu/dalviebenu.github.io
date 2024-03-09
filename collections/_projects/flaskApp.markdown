---
title:  "Ethical Hacking Admin Tool"
permalink: /projects/ethical-hacking-tool/
layout: page
---

## What is the Ethical Hacking Admin Tool?
The ethical hacking tool (referred internally as the flask app) was a tool that I designed to ease the workload on teaching assistants in the
ethical hacking course at KTH Royal Institute of Technology (where I did my bachelors).

The course was mainly practical, specifically, the course took the form of a capture the flag (CTF) competition. The students were given a set of
credentials and a simulation of a company's network. The students were then tasked with finding vulnerabilities in the network and exploiting them
to gain tokens. The tokens would be submitted and the more tokens a student gets, the higher their grade. However, there were hundreds of students
participating in the course and hence there were many instances of this corporate network (called worlds) hosted on the cloud. Whenever a host in a particular
world would go down, the students would reach out and ask for a restart of the host or world. The teaching assistants would then use an internally
developed CLI tool to conduct this restart. The CLI tool is able to connect to Google Cloud and make changes. It was found that most of the work done by the teaching assistants was to restart the worlds and hence it was
decided to create a tool that would allow the students to restart the worlds themselves.

## How does it work?
The flask app was a simple web application that was developed in python using the flask framework (hence the name). It was deployed on the cloud using docker and
kubernetes. The app would ask the students to upload their credentials (public encryption key signed by our CA file) and then it would use the internal CLI tool
to conduct this restart (which is hosted on its own docker container). The app would then send a message back to the student about the state of their world.
The app would also limit the number of restarts per person and track all the restarts conducted by the students (using a local sqlite database).

![login](/images/upload.png)
*Image 1 showing the login page of the ethical hacking admin tool*

A major challenge was integrating the app with the internal CLI tool. The CLI tool was itself a complex tool and was not designed to be used as a library.
However, since the CLI tool was launched using docker, I could use the docker python library to launch the CLI tool as a container and then use the docker python library
to send commands to the CLI tool. The next challenge was designing the UI as I had no limited experience in web development. I decided to keep the UI simple and only
included the necessary features. The app was then deployed on the cloud using docker and kubernetes.

![main](/images/main.png)
*Image 2 showing the main page of the ethical hacking admin tool*



## What did I learn?
I learned a lot about web development and cloud deployment as well as databases. I also learned a lot about docker and kubernetes. I also learnt about agile development
as I had to work with a PhD student and a professor to develop the app. I was able to hone my problem-solving skills as I had to integrate the app with the internal CLI
tool and work within the limitations of what was already available in the course (like the pre-existing RSA credentials given to the students to access the worlds). This led to some
interesting and innovative solutions.

Unfortunately, I cannot show the code for the app as it is proprietary to KTH.