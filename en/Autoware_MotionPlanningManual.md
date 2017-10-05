# Autoware Motion Planning Manual 

## For Autoware *ver.2017.Sep*

## Table of contents


This document explains motion planning features of Autoware. The document focuses on the local planner and controller.

# Overview of motion planning

Motion planning is a core task of an autonomous vehicle. Its purpose is to find control inputs to get the car from point A (the initial state) to point B (the goal state). Motion planning can be split into four subsystems:

1/ Global planning
2/ Behavior planning
3/ Local planning
4/ Control



Overall description of Openplanner is in the following paper from Nagoya university:

Darweesh, Hatem, Eijiro Takeuchi, Kazuya Takeda, Yoshiki Ninomiya, Adi Sujiwo, Luis Yoichi Morales, Naoki Akai, Tetsuo Tomizawa, and Shinpei Kato. "Open Source Integrated Planner for Autonomous Navigation in Highly Dynamic Environments." Journal of Robotics and Mechatronics 29, no. 4 (2017): 668-684.
https://www.fujipress.jp/jrm/rb/robot002900040668/



# Packages

*Before operating Autoware, ROS and Autoware are described in this chapter.*

