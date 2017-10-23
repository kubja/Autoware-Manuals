# Autoware Motion Planning Manual 

## For Autoware *ver.2017.Sep*

## Table of contents


This document explains motion planning features of Autoware. The document focuses on the local planner and controller.

# Overview of motion planning

Motion planning is a core task of an autonomous vehicle. Its purpose is to find control inputs to get the car from point A (the initial state) to point B (the goal state) given the sensor inputs. Motion planning can be split into four subproblems:

1. Global planning
2. Behavior planning
3. Local planning
4. Control

Currently, Autoware is powered by OpenPlanner developed by researchers from Nagoya university. OpenPlanner is based in lane graphs: it utilizes machine-generated or manually-created **vector maps** for global and local planning. The vector maps describe kinematically and dynamically viable paths in the environment.

# Setup


# OpenPlanner


Overall description of Openplanner is in the following paper from Nagoya university:

Darweesh, Hatem, Eijiro Takeuchi, Kazuya Takeda, Yoshiki Ninomiya, Adi Sujiwo, Luis Yoichi Morales, Naoki Akai, Tetsuo Tomizawa, and Shinpei Kato. "Open Source Integrated Planner for Autonomous Navigation in Highly Dynamic Environments." Journal of Robotics and Mechatronics 29, no. 4 (2017): 668-684.
https://www.fujipress.jp/jrm/rb/robot002900040668/


## Lane 

## Vector map

Vector map is specified by CSV files:

* area.csv: 
* crosswalk.csv:
* dtlane.csv:
* idx.csv:
* lane.csv: 
* line.csv: 
* node.csv: 
* point.csv: 
* signaldata.csv: 
* stopline.csv:
* vector.csv:


# Packages




*Description of Autoware packages related to *

