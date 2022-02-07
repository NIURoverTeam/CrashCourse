# Gui Timeline and Links to Fixed Tutorials

## (31 January 2022) Teams Message from Raven/Violet
As a refresher, for a few different reasons we're going to be building a web interface for the rover rather than a native linux app, so we're about to become very familiar with the Javascript programming language.
 
That's Javascript, not Java (similar name but unrelated), and you don't need to install anything to write some hello world code with it!  Just launch any web browser and open the developer console (typically F12), or create an HTML file with a script tag inside it.  Better yet, here's some tutorials.
* Beginner friendly: https://www.learn-js.org/
* Somewhat beginner friendly: https://www.tutorialspoint.com/javascript/index.htm
* Obtuse but full of information: https://www.w3schools.com/js/default.asp

I used Javascript extensively both professionally and personally, so I can probably answer any questions you might have regarding it.
Look into HTML and CSS as well, if you aren't familiar with them.  They'll be important for constructing the visual interface for our users.
 
Our web interface needs a way to interface with ROS, so here's the relevant library and protocol.  
* The classes and functions in the library we'll be using: http://robotwebtools.org/roslibjs/  
* Tutorials (outdated, ros1 instead of ros2) are available on this page: http://wiki.ros.org/roslibjs#tutorials  
* The protocol (rosbridge) which the library implements: https://wiki.ros.org/rosbridge_suite
 
Rosbridge has been installed on Shatterdome!

## (7 February 2022) Initial Converted Tutorial (WIP)

[Basic ROS2 and roslibjs Functionality](tutorial_basicrosfunctionality.md) (based on the corresponding [ROS1 Tutorial](http://wiki.ros.org/roslibjs/Tutorials/BasicRosFunctionality))

Notes for me, the process of converting the tutorial over:
1. Instaled NGINX on Shatterdome.
2. Cloned the roslibjs repo into `/var/www`, checked out tag `1.2.0`, so http://10.156.209.2/roslibjs/build/roslib.min.js is the path to the minified js lib file.
