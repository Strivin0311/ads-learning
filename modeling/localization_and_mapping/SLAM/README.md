# Simultaneous Localization and Mapping (SLAM)

This is an introduction about Simultaneous Localization and Mapping(SLAM), a technique used in robotics and autonomous vehicles to simultaneously construct or update a map of an unknown environment while keeping track of the vehicle's or robot's location within it.

The basic problem in SLAM is the chicken-and-egg: A map is needed to localize the vehicle, but at the same time, a position is needed to update the map. The key is to get these two processes to work together in real-time (hence "simultaneously").

SLAM techniques combine data from various sensors (like lidar, radar, or cameras) to both identify features in the environment and track movement. This can be a computationally challenging task, especially when the maps are large or the environments are changing rapidly, but successful SLAM is a crucial part of enabling autonomous robots and vehicles to move around in the world.


---

## Table of Contents
* [General SLAM](general.md)
* [Visual SLAM](visual.md)

---

For more detailed works, you can refer to [Simultaneous Localization And Mapping: A Survey of Current Trends in Autonomous Driving](https://hal.science/hal-01615897/file/2017-simultaneous_localization_and_mapping_a_survey_of_current_trends_in_autonomous_driving.pdf). 