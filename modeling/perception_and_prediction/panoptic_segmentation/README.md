# Panoptic Segmentation

This directory comprises methods on Panoptic Segmentation task, which aims to provide a comprehensive understanding of the driving environment by categorizing each pixel in an image into different semantic classes (Semantic Segmentation), as well as identifying and distinguishing each individual object of certain classes (Instance Segmentation).

To illustrate, semantic segmentation labels every pixel in an image to a certain class, like road, car, pedestrian, sky, etc. On the other hand, instance segmentation not only labels the class of every pixel, but also distinguishes different instances of the same class, identifying different cars in an image individually for instance.

Therefore, Panoptic Segmentation provides a unified view of the environment, not only recognizing the boundaries of the drivable area, recognize other vehicles, pedestrians, cyclists, and other elements in the scene, but also differentiate between instances of the same class, such as individual pedestrians in a crowd, which usually seems like a substitute task for [HD map](../../localization_and_mapping/HD_map/README.md).


#### Per-pixel classification is not all you need for semantic segmentation
the paper link is [here](https://proceedings.neurips.cc/paper_files/paper/2021/file/950a4152c2b4aa3ad78bdd6b366cc179-Paper.pdf).

#### Panoptic segmentation
the paper link is [here](https://openaccess.thecvf.com/content_CVPR_2019/papers/Kirillov_Panoptic_Segmentation_CVPR_2019_paper.pdf).

#### UPSNet: A Unified Panoptic Segmentation Network
the paper link is [here](https://openaccess.thecvf.com/content_CVPR_2019/papers/Xiong_UPSNet_A_Unified_Panoptic_Segmentation_Network_CVPR_2019_paper.pdf).

#### Panoptic segformer: Delving deeper into panoptic segmentation with transformers 
the paper link is [here](http://openaccess.thecvf.com/content/CVPR2022/papers/Li_Panoptic_SegFormer_Delving_Deeper_Into_Panoptic_Segmentation_With_Transformers_CVPR_2022_paper.pdf).

#### Masked-attention mask transformer for universal image segmentation
the paper link is [here](http://openaccess.thecvf.com/content/CVPR2022/papers/Cheng_Masked-Attention_Mask_Transformer_for_Universal_Image_Segmentation_CVPR_2022_paper.pdf).

---