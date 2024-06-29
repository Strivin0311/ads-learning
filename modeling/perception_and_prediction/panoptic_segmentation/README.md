# Panoptic Segmentation
*Here're some resources about Panoptic Segmentation for autonomous driving*

Intros:
* This directory comprises methods on Panoptic Segmentation task, which aims to provide a comprehensive understanding of the driving environment by categorizing each pixel in an image into different semantic classes (Semantic Segmentation), as well as identifying and distinguishing each individual object of certain classes (Instance Segmentation).

* To illustrate, semantic segmentation labels every pixel in an image to a certain class, like road, car, pedestrian, sky, etc. On the other hand, instance segmentation not only labels the class of every pixel, but also distinguishes different instances of the same class, identifying different cars in an image individually for instance.

* Therefore, Panoptic Segmentation provides a unified view of the environment, not only recognizing the boundaries of the drivable area, recognize other vehicles, pedestrians, cyclists, and other elements in the scene, but also differentiate between instances of the same class, such as individual pedestrians in a crowd, which usually seems like a substitute task for [HD map](../../localization_and_mapping/HD_map/README.md).

---

### Panoptic Segmentation

#### Remax: Relaxing for better training on efficient panoptic segmentation

paper link: [here](https://arxiv.org/pdf/2306.17319)

citation: 
```bibtex
@article{sun2023remax,
  title={Remax: Relaxing for better training on efficient panoptic segmentation},
  author={Sun, Shuyang and Wang, Weijun and Yu, Qihang and Howard, Andrew and Torr, Philip and Chen, Liang-Chieh},
  journal={arXiv preprint arXiv:2306.17319},
  year={2023}
}
```

#### Segment everything everywhere all at once (SEEM)

paper link: [here](https://arxiv.org/pdf/2304.06718.pdf)

citation: 
```bibtex
@article{zou2023segment,
  title={Segment everything everywhere all at once},
  author={Zou, Xueyan and Yang, Jianwei and Zhang, Hao and Li, Feng and Li, Linjie and Gao, Jianfeng and Lee, Yong Jae},
  journal={arXiv preprint arXiv:2304.06718},
  year={2023}
}
```

#### 4D Panoptic Scene Graph Generation (PSG-4D)

paper link: [here](https://openreview.net/pdf?id=GRHZiTbDDI)

citation: 
```bibtex
@inproceedings{yang2023d,
  title={4D Panoptic Scene Graph Generation},
  author={Jingkang Yang and Jun CEN and Wenxuan Peng and Shuai Liu and Fangzhou Hong and Xiangtai Li and Kaiyang Zhou and Qifeng Chen and Ziwei Liu},
  booktitle={Thirty-seventh Conference on Neural Information Processing Systems},
  year={2023},
  url={https://openreview.net/forum?id=GRHZiTbDDI}
}
```


#### Panoptic scene graph generation (PSG)

paper link: [here](https://arxiv.org/pdf/2207.11247)

citation: 
```bibtex
@inproceedings{yang2022panoptic,
  title={Panoptic scene graph generation},
  author={Yang, Jingkang and Ang, Yi Zhe and Guo, Zujin and Zhou, Kaiyang and Zhang, Wayne and Liu, Ziwei},
  booktitle={European Conference on Computer Vision},
  pages={178--196},
  year={2022},
  organization={Springer}
}
```

#### Panoptic segformer: Delving deeper into panoptic segmentation with transformers

paper link: [here](http://openaccess.thecvf.com/content/CVPR2022/papers/Li_Panoptic_SegFormer_Delving_Deeper_Into_Panoptic_Segmentation_With_Transformers_CVPR_2022_paper.pdf)

citation: 
```bibtex
@inproceedings{li2022panoptic,
  title={Panoptic segformer: Delving deeper into panoptic segmentation with transformers},
  author={Li, Zhiqi and Wang, Wenhai and Xie, Enze and Yu, Zhiding and Anandkumar, Anima and Alvarez, Jose M and Luo, Ping and Lu, Tong},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  pages={1280--1289},
  year={2022}
}
```

#### Upsnet: A unified panoptic segmentation network

paper link: [here](https://openaccess.thecvf.com/content_CVPR_2019/papers/Xiong_UPSNet_A_Unified_Panoptic_Segmentation_Network_CVPR_2019_paper.pdf)

citation: 
```bibtex
@inproceedings{xiong2019upsnet,
  title={Upsnet: A unified panoptic segmentation network},
  author={Xiong, Yuwen and Liao, Renjie and Zhao, Hengshuang and Hu, Rui and Bai, Min and Yumer, Ersin and Urtasun, Raquel},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  pages={8818--8826},
  year={2019}
}
```

#### Panoptic segmentation

paper link: [here](https://openaccess.thecvf.com/content_CVPR_2019/papers/Kirillov_Panoptic_Segmentation_CVPR_2019_paper.pdf)

citation: 
```bibtex
@inproceedings{kirillov2019panoptic,
  title={Panoptic segmentation},
  author={Kirillov, Alexander and He, Kaiming and Girshick, Ross and Rother, Carsten and Doll{\'a}r, Piotr},
  booktitle={Proceedings of the IEEE/CVF conference on computer vision and pattern recognition},
  pages={9404--9413},
  year={2019}
}
```


### Semantic Segmentation


#### Segment Any Point Cloud Sequences by Distilling Vision Foundation Models

paper link: [here](https://arxiv.org/pdf/2306.09347)

citation: 
```bibtex
@article{liu2023segment,
  title={Segment Any Point Cloud Sequences by Distilling Vision Foundation Models},
  author={Liu, Youquan and Kong, Lingdong and Cen, Jun and Chen, Runnan and Zhang, Wenwei and Pan, Liang and Chen, Kai and Liu, Ziwei},
  journal={arXiv preprint arXiv:2306.09347},
  year={2023}
}
```
    


#### Masked-attention mask transformer for universal image segmentation

paper link: [here](http://openaccess.thecvf.com/content/CVPR2022/papers/Cheng_Masked-Attention_Mask_Transformer_for_Universal_Image_Segmentation_CVPR_2022_paper.pdf)

citation: 
```bibtex
@inproceedings{cheng2022masked,
  title={Masked-attention mask transformer for universal image segmentation},
  author={Cheng, Bowen and Misra, Ishan and Schwing, Alexander G and Kirillov, Alexander and Girdhar, Rohit},
  booktitle={Proceedings of the IEEE/CVF conference on computer vision and pattern recognition},
  pages={1290--1299},
  year={2022}
}
```

#### Per-pixel classification is not all you need for semantic segmentation

paper link: [here](https://proceedings.neurips.cc/paper_files/paper/2021/file/950a4152c2b4aa3ad78bdd6b366cc179-Paper.pdf)

citation: 
```bibtex
@article{cheng2021per,
  title={Per-pixel classification is not all you need for semantic segmentation},
  author={Cheng, Bowen and Schwing, Alex and Kirillov, Alexander},
  journal={Advances in Neural Information Processing Systems},
  volume={34},
  pages={17864--17875},
  year={2021}
}
```


#### Cross-view semantic segmentation for sensing surroundings

paper link: [here](https://arxiv.org/pdf/1906.03560)

citation:

```bibtex
@article{Pan_2020,
   title={Cross-View Semantic Segmentation for Sensing Surroundings},
   volume={5},
   ISSN={2377-3774},
   url={http://dx.doi.org/10.1109/LRA.2020.3004325},
   DOI={10.1109/lra.2020.3004325},
   number={3},
   journal={IEEE Robotics and Automation Letters},
   publisher={Institute of Electrical and Electronics Engineers (IEEE)},
   author={Pan, Bowen and Sun, Jiankai and Leung, Ho Yin Tiga and Andonian, Alex and Zhou, Bolei},
   year={2020},
   month=jul, pages={4867–4873} 
}
```

#### Pointnet: Deep learning on point sets for 3d classification and segmentation

paper link: [here](https://openaccess.thecvf.com/content_cvpr_2017/papers/Qi_PointNet_Deep_Learning_CVPR_2017_paper.pdf)

citation: 
```bibtex
@inproceedings{qi2017pointnet,
  title={Pointnet: Deep learning on point sets for 3d classification and segmentation},
  author={Qi, Charles R and Su, Hao and Mo, Kaichun and Guibas, Leonidas J},
  booktitle={Proceedings of the IEEE conference on computer vision and pattern recognition},
  pages={652--660},
  year={2017}
}
```


### Instance Segmentation

#### Break-A-Scene: Extracting Multiple Concepts from a Single Image

paper link: [here](https://arxiv.org/pdf/2305.16311)

citation: 
```bibtex
@article{avrahami2023break,
  title={Break-A-Scene: Extracting Multiple Concepts from a Single Image},
  author={Avrahami, Omri and Aberman, Kfir and Fried, Ohad and Cohen-Or, Daniel and Lischinski, Dani},
  journal={arXiv preprint arXiv:2305.16311},
  year={2023}
}
```


#### High Quality Entity Segmentation

paper link: [here](http://openaccess.thecvf.com/content/ICCV2023/html/Qi_High_Quality_Entity_Segmentation_ICCV_2023_paper.html)

citation: 
```bibtex
@inproceedings{qi2023high,
  title={High Quality Entity Segmentation},
  author={Qi, Lu and Kuen, Jason and Shen, Tiancheng and Gu, Jiuxiang and Li, Wenbo and Guo, Weidong and Jia, Jiaya and Lin, Zhe and Yang, Ming-Hsuan},
  booktitle={Proceedings of the IEEE/CVF International Conference on Computer Vision},
  pages={4047--4056},
  year={2023}
}
```


     