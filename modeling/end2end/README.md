# End-to-End Autonomous Driving
*Here're some resources about End-to-End Autonomous Driving*


Intros:

* End-to-end autonomous driving is an approach where a single (large) model is responsible for controlling all aspects of the vehicle's operation, directly mapping sensor inputs to control outputs without any explicit breakdown of the task into sub-tasks like perception, prediction, and control(but maybe implicitly).

* In a typical end-to-end setup, the model might take raw or processed sensor data (like images from a camera or lidar point clouds) and directly output steering commands, acceleration, and braking. These models are often trained using supervised learning techniques, with data collected from humans driving in a variety of environments and conditions.

* End-to-end autonomous driving is seen as a potential alternative to the traditional modular pipeline used in most current self-driving systems. The modular pipeline breaks down the task of driving into a series of steps, each handled by a specialized module, like object detection, tracking, path planning, and control. While this approach provides interpretability and allows leveraging expert knowledge in designing and tuning each module, it also introduces potential points of failure where errors in one module can propagate and negatively affect subsequent modules.

* The main advantage of the end-to-end approach is its potential for simplicity and efficiency, as a single model can learn to perform the complex task of driving without the need for manual engineering of different stages in the pipeline. However, it also has several challenges. These include the difficulty of obtaining sufficient diverse and representative training data, the challenge of ensuring safety and reliability of a black-box model, and the current lack of interpretability of these models, which makes it difficult to diagnose and fix issues.

---

## Table of Contents
* [Driving with LLMs](./driving_with_llms.md)

---



#### Planning-oriented autonomous driving

paper link: [here](https://openaccess.thecvf.com/content/CVPR2023/papers/Hu_Planning-Oriented_Autonomous_Driving_CVPR_2023_paper.pdf)

citation: 
```bibtex
@inproceedings{hu2023planning,
  title={Planning-oriented autonomous driving},
  author={Hu, Yihan and Yang, Jiazhi and Chen, Li and Li, Keyu and Sima, Chonghao and Zhu, Xizhou and Chai, Siqi and Du, Senyao and Lin, Tianwei and Wang, Wenhai and others},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  pages={17853--17862},
  year={2023}
}
```
    

#### Model-based imitation learning for urban driving

paper link: [here](https://proceedings.neurips.cc/paper_files/paper/2022/file/827cb489449ea216e4a257c47e407d18-Paper-Conference.pdf)

citation: 
```bibtex
@article{hu2022model,
  title={Model-based imitation learning for urban driving},
  author={Hu, Anthony and Corrado, Gianluca and Griffiths, Nicolas and Murez, Zachary and Gurau, Corina and Yeo, Hudson and Kendall, Alex and Cipolla, Roberto and Shotton, Jamie},
  journal={Advances in Neural Information Processing Systems},
  volume={35},
  pages={20703--20716},
  year={2022}
}
```

#### St-p3: End-to-end vision-based autonomous driving via spatial-temporal feature learning

paper link: [here](https://arxiv.org/pdf/2207.07601)

citation: 
```bibtex
@inproceedings{hu2022st,
  title={St-p3: End-to-end vision-based autonomous driving via spatial-temporal feature learning},
  author={Hu, Shengchao and Chen, Li and Wu, Penghao and Li, Hongyang and Yan, Junchi and Tao, Dacheng},
  booktitle={European Conference on Computer Vision},
  pages={533--549},
  year={2022},
  organization={Springer}
}
```
    
    
#### Learning by watching

paper link: [here](https://openaccess.thecvf.com/content/CVPR2021/papers/Zhang_Learning_by_Watching_CVPR_2021_paper.pdf)

citation: 
```bibtex
@inproceedings{zhang2021learning,
  title={Learning by watching},
  author={Zhang, Jimuyang and Ohn-Bar, Eshed},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  pages={12711--12721},
  year={2021}
}
```

#### Multi-modal fusion transformer for end-to-end autonomous driving

paper link: [here](http://openaccess.thecvf.com/content/CVPR2021/papers/Prakash_Multi-Modal_Fusion_Transformer_for_End-to-End_Autonomous_Driving_CVPR_2021_paper.pdf)

citation: 
```bibtex
@inproceedings{prakash2021multi,
  title={Multi-modal fusion transformer for end-to-end autonomous driving},
  author={Prakash, Aditya and Chitta, Kashyap and Geiger, Andreas},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  pages={7077--7087},
  year={2021}
}
```
    
#### Mp3: A unified model to map, perceive, predict and plan

paper link: [here](https://openaccess.thecvf.com/content/CVPR2021/papers/Casas_MP3_A_Unified_Model_To_Map_Perceive_Predict_and_Plan_CVPR_2021_paper.pdf)

citation: 
```bibtex
@inproceedings{casas2021mp3,
  title={Mp3: A unified model to map, perceive, predict and plan},
  author={Casas, Sergio and Sadat, Abbas and Urtasun, Raquel},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  pages={14403--14412},
  year={2021}
}
```
    

#### End-to-end driving via conditional imitation learning

paper link: [here](https://arxiv.org/pdf/1710.02410)

citation: 
```bibtex
@inproceedings{codevilla2018end,
  title={End-to-end driving via conditional imitation learning},
  author={Codevilla, Felipe and M{\"u}ller, Matthias and L{\'o}pez, Antonio and Koltun, Vladlen and Dosovitskiy, Alexey},
  booktitle={2018 IEEE international conference on robotics and automation (ICRA)},
  pages={4693--4700},
  year={2018},
  organization={IEEE}
}
```
    

#### End to end learning for self-driving cars

paper link: [here](https://arxiv.org/pdf/1604.07316.pdf%5D)

citation: 
```bibtex
@article{bojarski2016end,
  title={End to end learning for self-driving cars},
  author={Bojarski, Mariusz and Del Testa, Davide and Dworakowski, Daniel and Firner, Bernhard and Flepp, Beat and Goyal, Prasoon and Jackel, Lawrence D and Monfort, Mathew and Muller, Urs and Zhang, Jiakai and others},
  journal={arXiv preprint arXiv:1604.07316},
  year={2016}
}
```
