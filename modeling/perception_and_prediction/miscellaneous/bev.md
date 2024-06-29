# Bird's Eye View Representaion
*Here're some resources about Bird's Eye View Representaion*

Intros:
* Bird's Eye View (BEV) representation is a crucial concept used in various tasks of autonomous driving systems, which provides a top-down perspective of the entities in the environment, typically including the vehicle itself, other dynamic entities (e.g., other vehicles, pedestrians, cyclists), and static elements (e.g., road boundaries, lane markings, traffic signs, buildings).

* The advantage of BEV representation is its ability to simplify complex 3D scenarios into a 2D plane, reducing the computational complexity of subsequent tasks. For instance, it allows easier identification of free space for navigation, object positioning, and trajectory prediction.

* However, it may also lose some information from the original 3D data, like the vertical dimension, which can be important for tasks like object recognition and precise localization. Hence, an optimal balance between complexity and information preservation is required when using BEV representation.

---

#### Tri-perspective view for vision-based 3d semantic occupancy prediction

paper link: [here](https://openaccess.thecvf.com/content/CVPR2023/papers/Huang_Tri-Perspective_View_for_Vision-Based_3D_Semantic_Occupancy_Prediction_CVPR_2023_paper.pdf)

citation: 
```bibtex
@inproceedings{huang2023tri,
  title={Tri-perspective view for vision-based 3d semantic occupancy prediction},
  author={Huang, Yuanhui and Zheng, Wenzhao and Zhang, Yunpeng and Zhou, Jie and Lu, Jiwen},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  pages={9223--9232},
  year={2023}
}
```
    

#### Bevfusion: Multi-task multi-sensor fusion with unified bird's-eye view representation

paper link: [here](https://arxiv.org/pdf/2205.13542)

citation: 
```bibtex
@inproceedings{liu2023bevfusion,
  title={Bevfusion: Multi-task multi-sensor fusion with unified bird's-eye view representation},
  author={Liu, Zhijian and Tang, Haotian and Amini, Alexander and Yang, Xinyu and Mao, Huizi and Rus, Daniela L and Han, Song},
  booktitle={2023 IEEE International Conference on Robotics and Automation (ICRA)},
  pages={2774--2781},
  year={2023},
  organization={IEEE}
}
```

#### BEVFormer v2: Adapting Modern Image Backbones to Bird's-Eye-View Recognition via Perspective Supervision

paper link: [here](http://openaccess.thecvf.com/content/CVPR2023/papers/Yang_BEVFormer_v2_Adapting_Modern_Image_Backbones_to_Birds-Eye-View_Recognition_via_CVPR_2023_paper.pdf)

citation: 
```bibtex
@inproceedings{yang2023bevformer,
  title={BEVFormer v2: Adapting Modern Image Backbones to Bird's-Eye-View Recognition via Perspective Supervision},
  author={Yang, Chenyu and Chen, Yuntao and Tian, Hao and Tao, Chenxin and Zhu, Xizhou and Zhang, Zhaoxiang and Huang, Gao and Li, Hongyang and Qiao, Yu and Lu, Lewei and others},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  pages={17830--17839},
  year={2023}
}
```

#### Bevformer: Learning bird's-eye-view representation from multi-camera images via spatiotemporal transformers

paper link: [here](https://arxiv.org/pdf/2203.17270.pdf%EF%BC%88BEVFormer%EF%BC%89)

citation: 
```bibtex
@inproceedings{li2022bevformer,
  title={Bevformer: Learning bird’s-eye-view representation from multi-camera images via spatiotemporal transformers},
  author={Li, Zhiqi and Wang, Wenhai and Li, Hongyang and Xie, Enze and Sima, Chonghao and Lu, Tong and Qiao, Yu and Dai, Jifeng},
  booktitle={European conference on computer vision},
  pages={1--18},
  year={2022},
  organization={Springer}
}
```
    

#### Bevfusion: A simple and robust lidar-camera fusion framework

paper link: [here](https://proceedings.neurips.cc/paper_files/paper/2022/file/43d2b7fbee8431f7cef0d0afed51c691-Paper-Conference.pdf)

citation: 
```bibtex
@article{liang2022bevfusion,
  title={Bevfusion: A simple and robust lidar-camera fusion framework},
  author={Liang, Tingting and Xie, Hongwei and Yu, Kaicheng and Xia, Zhongyu and Lin, Zhiwei and Wang, Yongtao and Tang, Tao and Wang, Bing and Tang, Zhi},
  journal={Advances in Neural Information Processing Systems},
  volume={35},
  pages={10421--10434},
  year={2022}
}
```

#### Vectornet: Encoding hd maps and agent dynamics from vectorized representation

paper link: [here](http://openaccess.thecvf.com/content_CVPR_2020/papers/Gao_VectorNet_Encoding_HD_Maps_and_Agent_Dynamics_From_Vectorized_Representation_CVPR_2020_paper.pdf)

citation: 
```bibtex
@inproceedings{gao2020vectornet,
  title={Vectornet: Encoding hd maps and agent dynamics from vectorized representation},
  author={Gao, Jiyang and Sun, Chen and Zhao, Hang and Shen, Yi and Anguelov, Dragomir and Li, Congcong and Schmid, Cordelia},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  pages={11525--11533},
  year={2020}
}
```


#### UniBEV: Multi-modal 3D Object Detection with Uniform BEV Encoders for Robustness against Missing Sensor Modalities
paper link: [here](https://arxiv.org/abs/2309.14516v1)

citation: 
```bibtex
@misc{wang2023unibev,
      title={UniBEV: Multi-modal 3D Object Detection with Uniform BEV Encoders for Robustness against Missing Sensor Modalities}, 
      author={Shiming Wang and Holger Caesar and Liangliang Nan and Julian F. P. Kooij},
      year={2023},
      eprint={2309.14516},
      archivePrefix={arXiv},
      primaryClass={cs.CV}
}
```
