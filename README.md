# CrashCourse2021
Learning how to program a Mars rover, one week at a time.

## Lesson Planning
This section is notes for how we want to run the crash course (and can be removed once our planning is complete). There are 15 weeks in a semester, so we should probably aim to complete the crash course in 10-ish weeks I think to give some leeway. These bullet points are meant to be **in order** of how we want to teach things. Feel free to make revisions as desired. :)

* Week 1: Get people on GitHub and the Teams programming channel. Decide on a programming meeting time (how long?)
   * Explain which repos we have in our GitHub organization
* Week 2: Getting Started (software installations)
   * installing Ubuntu for WSL2, Xserver setup (Drake likes testing with `xeyes`) ![image](https://user-images.githubusercontent.com/19244666/118378411-57a53280-b599-11eb-8840-1f77d6dd8646.png)
      * Raven likes `xclock` better I think they said? I'm cool with whatever
   * (other installations that can be postponed: NoMachine/TeamViewer for shatterdome access)
* Week 3: Basic Bash intro
   * Command structure (`$ command [-options] [arguments]`), basic filesystem, `pwd`, `mkdir`, `ls`, `cd`, `nano`, `cp`, `mv`, `rmdir`, `rm`, `man`. See our [Bash & Linux Crash Course](https://github.com/NIURoverTeam/Docs/blob/main/legacy/Bash-%26-Linux-Crash-Course.md) for more details.
   * (If we wanna get to the python tutorial sooner, we could do python in VS Code and postpone this until after)
* Week 4-5: Basic Python tutorial (do after git intro?)
   * Using Python's [turtle](https://www.geeksforgeeks.org/turtle-programming-python/) library?
      * Drake got it to work with just Ubuntu WSL2, [`sudo apt-get install python3-tk`](https://stackoverflow.com/questions/25905540/importerror-no-module-named-tkinter), and an Xserver running: ![image](https://user-images.githubusercontent.com/19244666/118378278-4a3b7880-b598-11eb-9842-7486c6f247cb.png)
      * If we want we can do this in VS Code instead of the terminal
      * Maybe have this be part of the git learning by tracking code in a branch? Might unnecessarily complicate the python learning though
* Week 6: GitHub (and git?) intro (do before python intro?)
   * read [What is Git?](https://dev.to/javascriptcoff1/what-is-git-4pmh)
   * Maybe have a chunk of code they clone (e.g. a python `turtle` function), modify, and then push their changes to a branch?
* Week 7: Docker conceptual intro (just to get it running and understand why we use it)
   * read [What is Docker?](https://dev.to/javascriptcoff1/what-is-docker-3be2)
   * running one of our ROS2 containers
      * check integrity with `ros2 doctor`
* Weeks 8-11: [ROS2 Beginner Tutorials: CLI Tools & Client Libraries](https://docs.ros.org/en/foxy/Tutorials.html) (but slightly out of order). Drake tentatively proposes the following tutorials order:
   * Some of the "Beginner: CLI Tools" tutorials:
      * Configuring your ROS 2 environment
      * Introducing turtlesim and rqt? (not sure if necessary. `rqt_graph` is introduced in "ROS 2 topics" tutorial)
         * challenge: some "check your understanding" questions. Can hide answer like so:
            <details>
              <summary>click to reveal answer</summary>
              hello world
            </details>
      * Understanding ROS 2 nodes
      * Understanding ROS 2 topics
   * Some of the "Beginner: Client Libraries" tutorials:
      * Creating a workspace
      * Creating your first ROS 2 package (not sure if necessary)
      * Writing a simple publisher and subscriber (Python)
         * challenge: modify the publisher so it says a different message
* Some weeks: more ROS2 tutorials (do this after Webots intro?)
   * understanding services
   * writing a simple service and client (python)
      * challenge: comment out AddTwoInts code, and create a SubtractTwoInts service
      * challenge: uncomment AddTwoInts code, and make a way for client to request one service or the other (modify the challenge if this is bad use of services)
* Some weeks: Webots intro (do this before more ROS2 tutorials?)
   * running a demo in Docker container (on shatterdome?) to verify integrity (and cuz it's cool)
   * quick intro to scene tree
   * writing code to communicate with robot controller
   * not in crash course, but further reading: https://cyberbotics.com/doc/guide/tutorials?tab-language=python

## Lessons
