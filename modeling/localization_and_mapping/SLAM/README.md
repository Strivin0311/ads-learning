# Simultaneous Localization and Mapping (SLAM)
*Here're some resources about Simultaneous Localization and Mapping (SLAM)*

Intros:
* This is an introduction about Simultaneous Localization and Mapping(SLAM), a technique used in robotics and autonomous vehicles to simultaneously construct or update a map of an unknown environment while keeping track of the vehicle's or robot's location within it.

* The basic problem in SLAM is the chicken-and-egg: A map is needed to localize the vehicle, but at the same time, a position is needed to update the map. The key is to get these two processes to work together in real-time (hence "simultaneously").

* SLAM techniques combine data from various sensors (like lidar, radar, or cameras) to both identify features in the environment and track movement. This can be a computationally challenging task, especially when the maps are large or the environments are changing rapidly, but successful SLAM is a crucial part of enabling autonomous robots and vehicles to move around in the world.


## Table of Contents
* [General SLAM](general.md)
* [Visual SLAM](visual.md)

---

#### Simultaneous localization and mapping: A survey of current trends in autonomous driving

paper link: [here](https://hal.science/hal-01615897/document)

citation: 
```bibtex
@article{bresson2017simultaneous,
  title={Simultaneous localization and mapping: A survey of current trends in autonomous driving},
  author={Bresson, Guillaume and Alsayed, Zayed and Yu, Li and Glaser, S{\'e}bastien},
  journal={IEEE Transactions on Intelligent Vehicles},
  volume={2},
  number={3},
  pages={194--220},
  year={2017},
  publisher={IEEE}
}
```