# CrashCourse2021
Learning how to program a Mars rover, one week at a time.

## Lesson Planning
This section is notes for how we want to run the crash course (and can be removed once our planning is complete). There are 15 weeks in a semester, so we should probably aim to complete the crash course in 10-ish weeks I think to give some leeway. These bullet points are meant to be **in order** of how we want to teach things. Feel free to make revisions as desired. :)

#### Week 1: Setting up communication
* Get people on GitHub and the Teams programming channel. Decide on a programming meeting time (how long?)
* Explain which repos we have in our GitHub organization

#### Week 2: Getting Started (software installations)
* If using Windows 10, install Ubuntu for WSL2 using [this guide](https://docs.microsoft.com/en-us/windows/wsl/install-win10#manual-installation-steps). When at "Step 6 - Install your Linux distribution of choice", choose Ubuntu from the Microsoft Store
* To set up an X-server for yourself, follow our [Installing an X-Server guide](https://github.com/NIURoverTeam/Docs/blob/main/Guides/Installing-an-X-Server.md) 
  * Drake likes testing with `xeyes` (make sure the Xserver is running first) ![image](https://user-images.githubusercontent.com/19244666/118378411-57a53280-b599-11eb-8840-1f77d6dd8646.png)
  * Raven likes `xclock` better I think they said? I'm cool with whatever
* (other installations that can be postponed: NoMachine/TeamViewer for shatterdome access)

#### Week 3: Basic Bash intro
* Command structure (`$ command [-options] [arguments]`), basic filesystem, `pwd`, `mkdir`, `ls`, `cd`, `nano`, `cp`, `mv`, `rmdir`, `rm`, `man`. See our [Bash & Linux Crash Course](https://github.com/NIURoverTeam/Docs/blob/main/legacy/Bash-%26-Linux-Crash-Course.md) for more details.
* (If we wanna get to the python tutorial sooner, we could do python in VS Code and postpone this until after)

#### Week 4-5: Basic Python tutorial (do after git intro?)
* Using Python's [turtle](https://www.geeksforgeeks.org/turtle-programming-python/) library
  * Drake got it to work with just Ubuntu WSL2, [`sudo apt-get install python3-tk`](https://stackoverflow.com/questions/25905540/importerror-no-module-named-tkinter), and an Xserver running
  * Start with this code:
    ```python3
    import turtle
    
    # setup 
    scrn = turtle.getscreen()
    turt = turtle.Turtle()
    
    # vvv YOUR CODE GOES BELOW HERE vvv
    
    
    
    # ^^^ YOUR CODE GOES ABOVE HERE ^^^
    
    # leave the screen open until clicked
    scrn.exitonclick()
    ```
  * Use these functions: `forward(amount)`, `backward(amount)`, `right(angle)`, `left(angle)`, `fillcolor(color_name)`, `begin_fill()`, `end_fill()`, `penup()` (picks up the turtle's pen), and/or `pendown()` (puts down the turtle's pen). More info and a few more functions can be found [here](https://www.geeksforgeeks.org/turtle-programming-python/). Make sure to call these functions from the Turtle object we instantiated in the starter code.
  * Challenges - make these drawings: 
    * Write the body for a function named `def colored_square(my_size, my_color):`, which draws a square of size `my_size` and color `my_color`. Then draw two squares using these two lines:
      ```python3
      colored_square(100, "blue")
      colored_square(50, "red")
      ```
      ![image](https://user-images.githubusercontent.com/19244666/134120816-6d271240-6c1d-48e9-90f5-5f1ad68cc2ab.png)
      <details>
        <summary>^^ Click to reveal source code for the above example. ^^</summary>
        ![image](https://user-images.githubusercontent.com/19244666/118378278-4a3b7880-b598-11eb-9842-7486c6f247cb.png)
      </details>
  
    * In a separate python file, write the body for a function named `def draw_polygon(num_sides):`, which draws a regular polygon with the requested number of sides (Hint: the angle to turn for each shape is `360.0 / num_sides`). Then call the function in a for-loop to draw everything from a triangle to an octagon.  ![image](https://user-images.githubusercontent.com/19244666/134121224-e38e87bd-df20-49e3-b7f5-9b32bb7d8dc8.png)
      <details>
        <summary>^^ Click to reveal source code for the above example. ^^</summary>
        ![image](https://user-images.githubusercontent.com/19244666/134120525-dd5f4654-0fd3-464a-9d7f-c962ebad3fcd.png)
      </details>
* If we want we can do this in VS Code instead of the terminal
* Maybe have this be part of the git learning by tracking code in a branch? Might unnecessarily complicate the python learning though

#### Week 6: GitHub (and git?) intro (do before python intro?)
* read [What is Git?](https://dev.to/javascriptcoff1/what-is-git-4pmh)
* Maybe have a chunk of code they clone (e.g. a python `turtle` function), modify, and then push their changes to a branch?

#### Weeks 7-10: [ROS2 Beginner Tutorials: CLI Tools & Client Libraries](https://docs.ros.org/en/foxy/Tutorials.html) (but slightly out of order). Drake tentatively proposes the following tutorials order:
> Note, to get ROS2 working on your computer, start your X-server, SSH into shatterdome with `ssh -X <username>@<shatterdome_ip>`, and then it should work. If off the campus's WiFi, first SSH into your Turing/Hopper account using `ssh -Y <username>@turing.cs.niu.edu` or `ssh -Y <username>@hopper.cs.niu.edu`, and then `ssh -X` to shatterdome as described above.

> Note, since we're SSH'ing into shatterdome which is a Linux machine, **always use the Linux instructions, _even if you're a MacOS or Windows user!!!_**
* Some of the "Beginner: CLI Tools" tutorials:
  * [Configuring your ROS 2 environment](https://docs.ros.org/en/foxy/Tutorials/Configuring-ROS2-Environment.html) (*Skip the instructions about installations, ROS2 is already installed on shatterdome!*)
    * (Do we need to set `ROS_DOMAIN_ID`? I guess ignore for now)
    * challenge: run `ros2 doctor`. Do you get a bunch of output and then `All 4 checks passed` at the bottom?
  * [Introducing turtlesim and rqt](https://docs.ros.org/en/foxy/Tutorials/Turtlesim/Introducing-Turtlesim.html)
    * challenge: some "check your understanding" questions. Can hide answer like so:
      <details>
        <summary>click to reveal answer</summary>
        hello world
      </details>
  * [Understanding ROS 2 nodes](https://docs.ros.org/en/foxy/Tutorials/Understanding-ROS2-Nodes.html)
  * [Understanding ROS 2 topics](https://docs.ros.org/en/foxy/Tutorials/Topics/Understanding-ROS2-Topics.html)
* Some of the "Beginner: Client Libraries" tutorials:
  * [Creating a workspace](https://docs.ros.org/en/foxy/Tutorials/Workspace/Creating-A-Workspace.html)
  * [Creating your first ROS 2 package](https://docs.ros.org/en/foxy/Tutorials/Creating-Your-First-ROS2-Package.html) (not sure if necessary)
  * [Writing a simple publisher and subscriber (Python)](https://docs.ros.org/en/foxy/Tutorials/Writing-A-Simple-Py-Publisher-And-Subscriber.html)
    * challenge: modify the publisher so it says a different message
    * challenge: write a publisher that controls the turtlesim to make shapes similar to what we did with the Python `turtle` library (color fill not necessary though)

#### Some weeks: more ROS2 tutorials (do this after Webots intro?)
* understanding services
* writing a simple service and client (python)
  * challenge: comment out AddTwoInts code, and create a SubtractTwoInts service
  * challenge: uncomment AddTwoInts code, and make a way for client to request one service or the other (modify the challenge if this is bad use of services)

#### Some weeks: Webots intro (do this before more ROS2 tutorials?)
* running a demo in Docker container (on shatterdome?) to verify integrity (and cuz it's cool)
* quick intro to scene tree
* writing code to communicate with robot controller
* not in crash course, but further reading: https://cyberbotics.com/doc/guide/tutorials?tab-language=python

---

### The Shadow Realm (AKA sections we decided not to pursue)
This area is for plans we decided to drop, but that we don't want to necessarily delete or bury in the commit history. Ideally, any sections added here should include a note for why they've been banished to The Shadow Realm<sup>:tm:</sup>.

#### Docker conceptual intro (just to get it running and understand why we use it)
* _(Banished because we discovered Docker was unnecessary for ROS2. Instead, we can just `ssh -X` into shatterdome with an X-server running locally, and it will work just fine.)_
* read [What is Docker?](https://dev.to/javascriptcoff1/what-is-docker-3be2)
* Install and test Docker in your terminal by following our [Installing Docker guide](https://github.com/NIURoverTeam/Docs/blob/main/Guides/Installing-Docker.md)
* running one of our ROS2 containers: follow the README instructions for running our [`ros2_foxy` Docker container](https://github.com/NIURoverTeam/Dockerfiles/tree/master/ros2_foxy) (you'll need to clone that `NIURoverTeam/Dockerfiles` repo in your WSL)
  * check integrity with `ros2 doctor`
