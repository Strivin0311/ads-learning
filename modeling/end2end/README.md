# End-to-End Autonomous Driving

End-to-end autonomous driving is an approach where a single (large) model is responsible for controlling all aspects of the vehicle's operation, directly mapping sensor inputs to control outputs without any explicit breakdown of the task into sub-tasks like perception, prediction, and control(but maybe implicitly).

In a typical end-to-end setup, the model might take raw or processed sensor data (like images from a camera or lidar point clouds) and directly output steering commands, acceleration, and braking. These models are often trained using supervised learning techniques, with data collected from humans driving in a variety of environments and conditions.

End-to-end autonomous driving is seen as a potential alternative to the traditional modular pipeline used in most current self-driving systems. The modular pipeline breaks down the task of driving into a series of steps, each handled by a specialized module, like object detection, tracking, path planning, and control. While this approach provides interpretability and allows leveraging expert knowledge in designing and tuning each module, it also introduces potential points of failure where errors in one module can propagate and negatively affect subsequent modules.

The main advantage of the end-to-end approach is its potential for simplicity and efficiency, as a single model can learn to perform the complex task of driving without the need for manual engineering of different stages in the pipeline. However, it also has several challenges. These include the difficulty of obtaining sufficient diverse and representative training data, the challenge of ensuring safety and reliability of a black-box model, and the current lack of interpretability of these models, which makes it difficult to diagnose and fix issues.


---

#### End to end learning for self-driving cars
the paper link is [here](https://arxiv.org/pdf/1604.07316.pdf).

#### End-to-end driving via conditional imitation learning
the paper link is [here](https://arxiv.org/pdf/1710.02410).

#### Model-based imitation learning for urban driving
the paper link is [here](https://proceedings.neurips.cc/paper_files/paper/2022/file/827cb489449ea216e4a257c47e407d18-Paper-Conference.pdf).

#### Learning by Watching
the paper link is [here](https://arxiv.org/pdf/2106.05966).

#### Multi-modal fusion transformer for end-to-end autonomous driving
the paper link is [here](http://openaccess.thecvf.com/content/CVPR2021/papers/Prakash_Multi-Modal_Fusion_Transformer_for_End-to-End_Autonomous_Driving_CVPR_2021_paper.pdf).

#### St-p3: End-to-end vision-based autonomous driving via spatial-temporal feature learning
the paper link is [here](https://arxiv.org/pdf/2207.07601).

#### Mp3: A unified model to map, perceive, predict and plan
the paper link is [here](https://openaccess.thecvf.com/content/CVPR2021/papers/Casas_MP3_A_Unified_Model_To_Map_Perceive_Predict_and_Plan_CVPR_2021_paper.pdf).

#### Planning-oriented Autonomous Driving
the paper link is [here](https://arxiv.org/pdf/2212.10156).
