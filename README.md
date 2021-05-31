# CrashCourse2021
Learning how to program a Mars rover, one week at a time.

## Lesson Planning
This section is notes for how we want to run the crash course (and can be removed once our planning is complete). There are 15 weeks in a semester, so we should probably aim to complete the crash course in 10-ish weeks I think to give some leeway. These bullet points are meant to be **in order** of how we want to teach things. Feel free to make revisions as desired. :)

1. Week 1: Maybe an intro to what the University Rover Challenge (URC) is?
   1. fun pictures
1. Week 2: Getting Started (software installations)
   1. installing Ubuntu for WSL2, Xserver setup (Drake likes testing with `xeyes`) ![image](https://user-images.githubusercontent.com/19244666/118378411-57a53280-b599-11eb-8840-1f77d6dd8646.png)
   2. (other installations that can be postponed: NoMachine)
1. Week 3: Basic Bash intro
   1. (If we wanna get to the python tutorial sooner, we could do python in VS Code and postpone this until after)
1. Week 4: GitHub (and git?) intro (read [What is Git?](https://dev.to/javascriptcoff1/what-is-git-4pmh))
   1. (If we wanna get to the python tutorial sooner, we could postpone this until after the python tutorial)
3. Week 5-6: Basic Python tutorial
   1. Using Python's [turtle](https://www.geeksforgeeks.org/turtle-programming-python/) library?
      1. Drake got it to work with just Ubuntu WSL2, [`sudo apt-get install python3-tk`](https://stackoverflow.com/questions/25905540/importerror-no-module-named-tkinter), and an Xserver running: ![image](https://user-images.githubusercontent.com/19244666/118378278-4a3b7880-b598-11eb-9842-7486c6f247cb.png)
      3. If we want we can do this in VS Code instead of the terminal
      4. Maybe have this be part of the git learning by tracking code in a branch? Might unnecessarily complicate the python learning though
4. Week 7: Docker conceptual intro
   1. read [What is Docker?](https://dev.to/javascriptcoff1/what-is-docker-3be2)
   1. running one of our ROS2 containers
      1. check integrity with `ros2 doctor`
5. Weeks 8-11: [ROS2 Beginner Tutorials: CLI Tools & Client Libraries](https://docs.ros.org/en/foxy/Tutorials.html) (but slightly out of order). Drake tentatively proposes the following tutorials order:
   1. Some of the "Beginner: CLI Tools" tutorials:
      1. Configuring your ROS 2 environment
      1. Introducing turtlesim and rqt? (not sure if necessary. `rqt_graph` is introduced in "ROS 2 topics" tutorial)
         1. challenge: some "check your understanding" questions. Can hide answer like so:
            <details>
              <summary>click to reveal answer</summary>
              hello world
            </details>
      3. Understanding ROS 2 nodes
      4. Understanding ROS 2 topics
   1. Some of the "Beginner: Client Libraries" tutorials:
      1. Creating a workspace
      2. Creating your first ROS 2 package (not sure if necessary)
      6. Writing a simple publisher and subscriber (Python)
         1. challenge: modify the publisher so it says a different message
6. Some weeks: Webots intro
   1. running a demo in Docker container (on shatterdome?) to verify integrity (and cuz it's cool)
   2. quick intro to scene tree
   3. writing code to communicate with robot controller
   4. not in crash course, but further reading: https://cyberbotics.com/doc/guide/tutorials?tab-language=python
7. Some weeks: more ROS2 tutorials
   1. understanding services
   8. writing a simple service and client (python)
      1. challenge: comment out AddTwoInts code, and create a SubtractTwoInts service
      2. challenge: uncomment AddTwoInts code, and make a way for client to request one service or the other (modify the challenge if this is bad use of services)

## Lessons
