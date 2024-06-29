# Planning & Control
*Here're some resources about Planning & Control*

Intros:
* Planning and Control are the final stages of the decision-making pipeline, directly affecting the vehicle's real-world movements. Once the environment is perceived and understood and the trajectories of other dynamic entities are predicted, the system can plan its actions and control the vehicle accordingly.

* In more details, Planning is the process of determining what actions the vehicle should take in response to the current and predicted future states of the environment. This involves defining a safe, efficient, and comfortable path for the vehicle to follow from its current position to its intended destination, while obeying traffic rules and avoiding obstacles. The level of complexity can vary significantly, from high-level route planning (e.g., deciding which streets to take) to more granular behavior planning (e.g., deciding how to change lanes, turn at intersections, or overtake other vehicles), and the lowest-level trajectory planning(a set of consecutive waypoints with timestamps).

* Control, on the other hand, is the process of implementing the planned path by sending commands, including throttle, brake, and steering, to the vehicle's actuation systems. The control module aims to follow the path planned by the planning module as accurately as possible while maintaining a smooth and comfortable ride, compensating for real-world disturbances such as road conditions, wind, and vehicle dynamics.


## Table of Contents
* [Planning](planning/README.md)
  * [Graph-based methods](planning/graph_based.md)
  * [Sampling-based methods](planning/sampling_based.md)
  * [ML-based methods](planning/ML_based.md)
* [Control](control/README.md)
  * [PID Control](control/PID.md)
  * [LQR Control](control/LQR.md)
  * [Model Predictive Control](control/MPC.md)
  * [NN-based Control](NN_based.md)
* [Vehicle Dynamics](vehicle_dynamics/README.md)

---

#### A survey of motion planning and control techniques for self-driving urban vehicles

paper link: [here](https://arxiv.org/pdf/1604.07446)

citation: 
```bibtex
@article{paden2016survey,
  title={A survey of motion planning and control techniques for self-driving urban vehicles},
  author={Paden, Brian and {\v{C}}{\'a}p, Michal and Yong, Sze Zheng and Yershov, Dmitry and Frazzoli, Emilio},
  journal={IEEE Transactions on intelligent vehicles},
  volume={1},
  number={1},
  pages={33--55},
  year={2016},
  publisher={IEEE}
}
```
    

#### 自动驾驶汽车决策与控制
book link: [here](https://pan.baidu.com/s/1NzGlsmQqV5hbloFI11QKDg), with extraction code: `rbp5`


