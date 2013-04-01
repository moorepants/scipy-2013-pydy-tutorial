================================
Dynamics and Control with Python
================================

A SciPy 2013 Tutorial Submission

Bio
===

Jason K. Moore received his Ph.D. and M.S. degrees from the University of
California, Davis in Mechanical and Aeronautical Engineering and his B.S. at Old
Dominion University in Norfolk, VA. His dissertation was titled “Human Control
of a Bicycle” and his doctoral work spanned a collaborative project involving
the theory of bicycle dynamics, control, and handling with experimental
validation. His research interests include topics in man–machine interaction,
manual control theory, multibody systems, human biomechanics, human power,
system identification, open science, and computer programming for scientists.
During 2008-09 he was a visiting Fulbright scholar to the Netherlands where he
was a researcher at Delft University of Technology. Jason is also a strong
advocate for opening up our science to the world. He co-founded the UC Davis
Open Science Group where he has co-hosted many prominent leaders in the Open
Science movement for presentations, discussions, and workshops.

Tutorial Description
====================

*A description of the tutorial, suitable for posting on the SciPy website for
attendees to view. It should include the target audience, the expected level of
knowledge prior to the class, and the goals of the class.*

In this tutorial we will first learn how to solve, simulate, and visualize
multibody dynamics problems with Python. These methods and techniques play an
important role in the design of robots, vehicles, spacecraft, manufacturing
machines, etc. In particular, we will highlight the derivation of realistic
models of motion with SymPy Mechanics. We will walk through the derivation of
the equations of motion of a multibody system (i.e. the model or the plant),
simulating and visualizing the free motion of the system, and finally we will
add simple feedback controllers to control the plants that we derive. We will
start with some simple college level physics problems such as the pendulum and
mass spring damper and close with a more complex three dimensional problem, such
as the control of a robotic arm.

It is best if the attendees have some background with calculus-based college
level physics. They should also be familiar with the SciPy Stack, in particular
IPython, SymPy, and SciPy. Our goal is that attendees will come away with the
ability to model basic multibody systems, simulate and visualize the motion, and
apply simple feedback controllers all in a Python framework.

Outline
=======

*A more detailed outline of the tutorial content, including the duration of each
part, and exercise sessions. Please include a description of how you plan to
make the tutorial hands-on.*

We will work through two parallel but similar problems in the tutorial. The
first will be a demonstration problem in which the full solutions will be shown
and each step will be explained, the second will be a similar problem that the
attendees will work in pairs to come up with the solution. I’ll introduce each
stage of the problem derivation and development in short ~5-10 minute sections
and then have the attendees complete the derivation of their problem using the
software tools that have been presented.

1. [00:00] Introduction

   - A wee bit about the presenter
   - Attendees introduce themselves to their neighbor and pair up

2. [00:05] Brief introduction to multibody systems and controls

   - Newton’s Laws, reference frames, velocity, acceleration, forces/torques
   - Ordinary differential equations and their solutions
   - Briefly mention control, but detail it later in talk.
   - Applications: robots, vehicles, etc

3. [00:10] Brief intro to the software stack (SymPy, SciPy, python-control)

   - SymPy and the Mechanics package
   - SciPy for ODE integration (scipy.ode)
   - matplotlib for 2D plotting and basic animation
   - IPython Notebook for interactive work
   - python-control for control design
   - Check to see everyone can import all of these and the versions are high
     enough

4. [00:15] Derivation of a simple two body 2D problem by hand (the example
   problem)

   - This will be done on a chalkboard, whiteboard, large paper, or overhead
     projector

5. [00:25] Exercise: Draw free body diagram of a two body 2D problem (the
   exercise problem)
6. [00:40] Intro to SymPy Mechanics with a derivation of the simple 2D two body
   problem with SymPy Mechanics
7. [00:50] Exercise: Derive equations of motion of simple 2D problem using SymPy
   Mechanics
8. [01:05] ODE integration routine overview and various Python packages (scipy,
   assimulo, pydstool, sundials, etc)
9. [01:15] Simulate the example problem with SciPy
10. [01:25] Exercise: Simulate the exercise problem
11. [01:40] 2D plotting of the state trajectories with matplotlib
12. [01:45] Excercise: Plot the simulation results of the exercise problem
13. [01:55] Demonstrate 2D animation the free motion of the example model with
    matplotlib
14. [02:10] Exercise: Animate the 2D exercise problem
15. [02:25] Explain linearization about an equilibrium point and demo with the
    example problem
16. [02:35] Exercise: Linearize the exercise problem
17. [02:45] Brief introduction to control theory and python-control
18. [02:55] Build a controller for the sample problem with python control
19. [03:05] Exercise: make controller for the exercise problem
20. [03:20] Add tracking control to the problem
21. [03:30] Exercise: add tracking control to student’s problem
22. [03:45] Demonstrate example of 3D dimensional problem, automation with
    Kane’s method and Lagrange’s method

Package List
============

*A list of Python packages that attendees will need to have installed prior to
the class to follow along. Please mention if any packages are not cross
platform. Installation instructions or links to installation documentation
should be provided for packages that are not available through easy_install,
pip, EPD, Anaconda, etc., or that require third party libraries.*

It will be sufficient to install the necessary software from the latest
scientific python distributions or your operating systems package manager with
the exception for two packages: SymPy and python-control.

Make sure you have relatively new stable releases of these packages from your
distribution or package manager:

| SciPy >0.10.1
| NumPy >1.6.2
| matplotlib >1.1.1
| IPython [notebook] >0.13
|

Special install instructions
----------------------------

SymPy
~~~~~

SymPy has a slow release schedule so we want to have the latest code to utilize
the latest features in the mechanics module. Install the latest version with
the following terminal commands.

With git::

$ git clone git://github.com/sympy/sympy.git

or without git::

$ wget https://github.com/sympy/sympy/archive/master.zip
$ unzip master.zip

::

$ cd sympy # or cd master
$ python setup.py install # use sudo if you want/need to

python-control
~~~~~~~~~~~~~~

::

$ wget http://downloads.sourceforge.net/project/python-control/control-0.6c.tar.gz
$ tar -zxvf control-0.6c.tar.gz
$ cd control-0.6c
$ python setup.py install

Documentation
=============

*If available, URL links to tutorial notes, slides, exercise files, ipython
notebooks, that you already have, even if they are preliminary.*

I do not have the tutorial materials prepared yet, but it will be very similar
in nature to this blog post/ipython notebook:
http://www.moorepants.info/blog/npendulum.html but structured for beginners. All
of the materials will be hosted at
https://github.com/moorepants/scipy-2013-pydy-tutorial.
