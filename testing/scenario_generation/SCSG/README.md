# Safety-Critical Scenario Generation
*Here're some resources about Safety-Critical Scenario Generation*

Intros:

* Safety-Critical Scenario Generation(SCSG) refers to the process of creating and simulating a variety of complex and high-risk situations that an autonomous vehicle(AV) might encounter on the road, including sudden braking, unexpected pedestrian movements, challenging weather conditions, or more complex traffic situations.

* The primary goal of safety-critical scenario generation is to assess and enhance the robustness, reliability, and safety of the AV systems before they're deployed in real-world environments. It is crucial because these scenarios are rare but have significant implications on the safety and trustworthiness of AVs.

* Typically, the process involves leveraging a mix of real-world data, simulated environments, and probabilistic modeling. Often, machine learning techniques are applied to generate a wide variety of scenarios and edge cases, reflecting the unpredictable nature of real-world driving.

* Historical traffic data and incident reports can be used as a foundation for generating safety-critical scenarios. This data can be augmented with simulated environmental factors, such as different weather conditions, lighting conditions, or road conditions.

* Safety-critical scenario generation can be seen as an essential part of the overall testing and validation process for autonomous driving systems. It can help identify potential weaknesses or blind spots in the AV system's perception, prediction, and decision-making modules and contribute to the ongoing improvement of these systems' safety and reliability.

## Table of Contents
* [Data-driven Methods](data_driven/README.md)
  * [Direct Sampling](data_driven/direct_sampling.md)
  * [Density Estimation](data_driven/density_estimate.md)
  * [RL-based](data_driven/rl_based.md)
* [Miscellaneous Methods](miscellaneous/README.md)
  * [Collision-Avoidance](miscellaneous/README.md#collision-avoidance)
  * [Adversarial Generation](miscellaneous/README.md#adversarial-generation)
  * [Knowledge-based Methods](miscellaneous/README.md#knowledge-based-methods)


---


#### A survey on safety-critical driving scenario generation—A methodological perspective

paper link: [here](https://arxiv.org/pdf/2202.02215)

citation: 
```bibtex
@article{ding2023survey,
  title={A survey on safety-critical driving scenario generation—A methodological perspective},
  author={Ding, Wenhao and Xu, Chejian and Arief, Mansur and Lin, Haohong and Li, Bo and Zhao, Ding},
  journal={IEEE Transactions on Intelligent Transportation Systems},
  year={2023},
  publisher={IEEE}
}
```
    

#### Finding critical scenarios for automated driving systems: A systematic literature review

paper link: [here](https://arxiv.org/pdf/2110.08664)

citation: 
```bibtex
@article{zhang2021finding,
  title={Finding critical scenarios for automated driving systems: A systematic literature review},
  author={Zhang, Xinhai and Tao, Jianbo and Tan, Kaige and T{\"o}rngren, Martin and S{\'a}nchez, Jos{\'e} Manuel Gaspar and Ramli, Muhammad Rusyadi and Tao, Xin and Gyllenhammar, Magnus and Wotawa, Franz and Mohan, Naveen and others},
  journal={arXiv preprint arXiv:2110.08664},
  year={2021}
}
```
    