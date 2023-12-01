# Panoptic Segmentation
*Here's some resources about Panoptic Segmentation*

Intros:
* This directory comprises methods on Panoptic Segmentation task, which aims to provide a comprehensive understanding of the driving environment by categorizing each pixel in an image into different semantic classes (Semantic Segmentation), as well as identifying and distinguishing each individual object of certain classes (Instance Segmentation).

* To illustrate, semantic segmentation labels every pixel in an image to a certain class, like road, car, pedestrian, sky, etc. On the other hand, instance segmentation not only labels the class of every pixel, but also distinguishes different instances of the same class, identifying different cars in an image individually for instance.

* Therefore, Panoptic Segmentation provides a unified view of the environment, not only recognizing the boundaries of the drivable area, recognize other vehicles, pedestrians, cyclists, and other elements in the scene, but also differentiate between instances of the same class, such as individual pedestrians in a crowd, which usually seems like a substitute task for [HD map](../../localization_and_mapping/HD_map/README.md).

---

#### High Quality Entity Segmentation [`UNREAD`]

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
    


#### Break-A-Scene: Extracting Multiple Concepts from a Single Image [`UNREAD`]

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



#### Panoptic segformer: Delving deeper into panoptic segmentation with transformers [`UNREAD`]

paper link: [here](http://openaccess.thecvf.com/content/CVPR2022/papers/Li_Panoptic_SegFormer_Delving_Deeper_Into_Panoptic_Segmentation_With_Transformers_CVPR_2022_paper.pdf)

citation: [here](./SegFormer.md)
```bibtex
@inproceedings{li2022panoptic,
  title={Panoptic segformer: Delving deeper into panoptic segmentation with transformers},
  author={Li, Zhiqi and Wang, Wenhai and Xie, Enze and Yu, Zhiding and Anandkumar, Anima and Alvarez, Jose M and Luo, Ping and Lu, Tong},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  pages={1280--1289},
  year={2022}
}
```

#### Masked-attention mask transformer for universal image segmentation [`UNREAD`]

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

#### Per-pixel classification is not all you need for semantic segmentation [`UNREAD`]

paper link: [here](https://proceedings.neurips.cc/paper_files/paper/2021/file/950a4152c2b4aa3ad78bdd6b366cc179-Paper.pdf)

citation: [here](./Maskformer.md)
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

#### Panoptic segmentation [`READ`]

paper link: [here](https://openaccess.thecvf.com/content_CVPR_2019/papers/Kirillov_Panoptic_Segmentation_CVPR_2019_paper.pdf)

citation: [here](./panoptic_segmentation.md)
```bibtex
@inproceedings{kirillov2019panoptic,
  title={Panoptic segmentation},
  author={Kirillov, Alexander and He, Kaiming and Girshick, Ross and Rother, Carsten and Doll{\'a}r, Piotr},
  booktitle={Proceedings of the IEEE/CVF conference on computer vision and pattern recognition},
  pages={9404--9413},
  year={2019}
}
```
    
#### Upsnet: A unified panoptic segmentation network [`UNREAD`]

paper link: [here](https://openaccess.thecvf.com/content_CVPR_2019/papers/Xiong_UPSNet_A_Unified_Panoptic_Segmentation_Network_CVPR_2019_paper.pdf)

citation: [here](./UPSNet.md)
```bibtex
@inproceedings{xiong2019upsnet,
  title={Upsnet: A unified panoptic segmentation network},
  author={Xiong, Yuwen and Liao, Renjie and Zhao, Hengshuang and Hu, Rui and Bai, Min and Yumer, Ersin and Urtasun, Raquel},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  pages={8818--8826},
  year={2019}
}
```

#### Panoptic, Instance and Semantic Relations: A Relational Context Encoder to Enhance Panoptic Segmentation [`READ`]

paper link: [here](https://openaccess.thecvf.com/content/CVPR2022/papers/Borse_Panoptic_Instance_and_Semantic_Relations_A_Relational_Context_Encoder_To_CVPR_2022_paper.pdf)

citation: [here](./Panoptic_Instance_and_Semantic_Relations.md)
```bibtex
@inproceedings{,
  title={Panoptic, Instance and Semantic Relations: A Relational Context Encoder to Enhance Panoptic Segmentation},
  author={},
  booktitle={},
  pages={1269--1279},
  year={2022}
}
```