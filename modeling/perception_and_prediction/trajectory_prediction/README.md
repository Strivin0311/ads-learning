# Trajectory Prediction
*Here're some resources about Trajectory Prediction*

Intros:
* This directory is about the methodology of Trajectory Prediction task in the prediction stage, that is concerned with forecasting the future movements of surrounding dynamic entities such as vehicles, pedestrians, and cyclists. This task is fundamental for safe and efficient navigation, as it helps the autonomous vehicle to anticipate potential changes in the environment and make timely, proactive driving decisions.


* In more detail, Trajectory Prediction involves generating plausible future paths for each detected object based on its current and historical states, such as its position, velocity, acceleration, and heading direction. Moreover, it also considers the object's interactions with the environment and other objects to account for the context and behavior patterns.

* For instance, a trajectory prediction module might predict that a pedestrian standing on the sidewalk near a crosswalk might cross the road in the near future, or a vehicle signaling a lane change will move into the adjacent lane. By making these predictions, the autonomous driving system can plan its actions accordingly to avoid potential collisions and ensure a smooth and safe ride.

* Due to the complexity and uncertainty of real-world scenarios, trajectory prediction remains a challenging problem, requiring robust methods that can handle diverse scenarios and take into account the inherently probabilistic nature of human behavior.

---

#### ViP3D: End-to-end visual trajectory prediction via 3d agent queries [`UNREAD`]

paper link: [here](http://openaccess.thecvf.com/content/CVPR2023/papers/Gu_ViP3D_End-to-End_Visual_Trajectory_Prediction_via_3D_Agent_Queries_CVPR_2023_paper.pdf)

citation: 
```bibtex
@inproceedings{gu2023vip3d,
  title={ViP3D: End-to-end visual trajectory prediction via 3d agent queries},
  author={Gu, Junru and Hu, Chenxu and Zhang, Tianyuan and Chen, Xuanyao and Wang, Yilun and Wang, Yue and Zhao, Hang},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  pages={5496--5506},
  year={2023}
}
```
    


#### SGCN: Sparse graph convolution network for pedestrian trajectory prediction [`UNREAD`]

paper link: [here](https://openaccess.thecvf.com/content/CVPR2021/papers/Shi_SGCN_Sparse_Graph_Convolution_Network_for_Pedestrian_Trajectory_Prediction_CVPR_2021_paper.pdf)

citation: 
```bibtex
@inproceedings{shi2021sgcn,
  title={SGCN: Sparse graph convolution network for pedestrian trajectory prediction},
  author={Shi, Liushuai and Wang, Le and Long, Chengjiang and Zhou, Sanping and Zhou, Mo and Niu, Zhenxing and Hua, Gang},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  pages={8994--9003},
  year={2021}
}
```
    

#### Shared cross-modal trajectory prediction for autonomous driving [`READ`]

paper link: [here](http://openaccess.thecvf.com/content/CVPR2021/papers/Choi_Shared_Cross-Modal_Trajectory_Prediction_for_Autonomous_Driving_CVPR_2021_paper.pdf)

citation: 
```bibtex
@inproceedings{choi2021shared,
  title={Shared cross-modal trajectory prediction for autonomous driving},
  author={Choi, Chiho and Choi, Joon Hee and Li, Jiachen and Malla, Srikanth},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  pages={244--253},
  year={2021}
}
```
    

#### Divide-and-conquer for lane-aware diverse trajectory prediction [`UNREAD`]

paper link: [here](https://openaccess.thecvf.com/content/CVPR2021/papers/Narayanan_Divide-and-Conquer_for_Lane-Aware_Diverse_Trajectory_Prediction_CVPR_2021_paper.pdf)

citation: 
```bibtex
@inproceedings{narayanan2021divide,
  title={Divide-and-conquer for lane-aware diverse trajectory prediction},
  author={Narayanan, Sriram and Moslemi, Ramin and Pittaluga, Francesco and Liu, Buyu and Chandraker, Manmohan},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  pages={15799--15808},
  year={2021}
}
```

#### Pedestrian and ego-vehicle trajectory prediction from monocular camera [`UNREAD`]

paper link: [here](https://openaccess.thecvf.com/content/CVPR2021/papers/Neumann_Pedestrian_and_Ego-Vehicle_Trajectory_Prediction_From_Monocular_Camera_CVPR_2021_paper.pdf)

citation: 
```bibtex
@inproceedings{neumann2021pedestrian,
  title={Pedestrian and ego-vehicle trajectory prediction from monocular camera},
  author={Neumann, Lukas and Vedaldi, Andrea},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  pages={10204--10212},
  year={2021}
}
```

#### Safe local motion planning with self-supervised freespace forecasting [`UNREAD`]

paper link: [here](http://openaccess.thecvf.com/content/CVPR2021/papers/Hu_Safe_Local_Motion_Planning_With_Self-Supervised_Freespace_Forecasting_CVPR_2021_paper.pdf)

citation: 
```bibtex
@inproceedings{hu2021safe,
  title={Safe local motion planning with self-supervised freespace forecasting},
  author={Hu, Peiyun and Huang, Aaron and Dolan, John and Held, David and Ramanan, Deva},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  pages={12732--12741},
  year={2021}
}
```

#### Lookout: Diverse multi-future prediction and planning for self-driving [`READ`]

paper link: [here](http://openaccess.thecvf.com/content/ICCV2021/papers/Cui_LookOut_Diverse_Multi-Future_Prediction_and_Planning_for_Self-Driving_ICCV_2021_paper.pdf)

citation: 
```bibtex
@inproceedings{cui2021lookout,
  title={Lookout: Diverse multi-future prediction and planning for self-driving},
  author={Cui, Alexander and Casas, Sergio and Sadat, Abbas and Liao, Renjie and Urtasun, Raquel},
  booktitle={Proceedings of the IEEE/CVF International Conference on Computer Vision},
  pages={16107--16116},
  year={2021}
}
```
    
#### Pnpnet: End-to-end perception and prediction with tracking in the loop [`READ`]

paper link: [here](https://openaccess.thecvf.com/content_CVPR_2020/papers/Liang_PnPNet_End-to-End_Perception_and_Prediction_With_Tracking_in_the_Loop_CVPR_2020_paper.pdf)

citation: 
```bibtex
@inproceedings{liang2020pnpnet,
  title={Pnpnet: End-to-end perception and prediction with tracking in the loop},
  author={Liang, Ming and Yang, Bin and Zeng, Wenyuan and Chen, Yun and Hu, Rui and Casas, Sergio and Urtasun, Raquel},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  pages={11553--11562},
  year={2020}
}
```
    
    
    
#### Motion estimation for self-driving cars with a generalized camera [`UNREAD`]

paper link: [here](https://openaccess.thecvf.com/content_cvpr_2013/papers/Lee_Motion_Estimation_for_2013_CVPR_paper.pdf)

citation: 
```bibtex
@inproceedings{hee2013motion,
  title={Motion estimation for self-driving cars with a generalized camera},
  author={Hee Lee, Gim and Faundorfer, Friedrich and Pollefeys, Marc},
  booktitle={Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition},
  pages={2746--2753},
  year={2013}
}
```

