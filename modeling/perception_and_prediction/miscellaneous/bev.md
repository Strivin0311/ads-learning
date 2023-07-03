# BEV Representaion

Bird's Eye View (BEV) representation is a crucial concept used in various tasks of autonomous driving systems, which provides a top-down perspective of the entities in the environment, typically including the vehicle itself, other dynamic entities (e.g., other vehicles, pedestrians, cyclists), and static elements (e.g., road boundaries, lane markings, traffic signs, buildings).

The advantage of BEV representation is its ability to simplify complex 3D scenarios into a 2D plane, reducing the computational complexity of subsequent tasks. For instance, it allows easier identification of free space for navigation, object positioning, and trajectory prediction.

However, it may also lose some information from the original 3D data, like the vertical dimension, which can be important for tasks like object recognition and precise localization. Hence, an optimal balance between complexity and information preservation is required when using BEV representation.

#### Bevfusion: A simple and robust lidar-camera fusion framework
the paper link is [here](https://proceedings.neurips.cc/paper_files/paper/2022/file/43d2b7fbee8431f7cef0d0afed51c691-Paper-Conference.pdf).

#### BEVFusion: Multi-Task Multi-Sensor Fusion with Unified Bird's-Eye View Representation
the paper link is [here](https://arxiv.org/pdf/2205.13542).

#### Bevformer: Learning bird's-eye-view representation from multi-camera images via spatiotemporal transformers
the paper link is [here](https://arxiv.org/pdf/2203.17270.pdf).

#### BEVFormer v2: Adapting Modern Image Backbones to Bird's-Eye-View Recognition via Perspective Supervision
the paper link is [here](http://openaccess.thecvf.com/content/CVPR2023/papers/Yang_BEVFormer_v2_Adapting_Modern_Image_Backbones_to_Birds-Eye-View_Recognition_via_CVPR_2023_paper.pdf).

#### Vectornet: Encoding hd maps and agent dynamics from vectorized representation
the paper link is [here](http://openaccess.thecvf.com/content_CVPR_2020/papers/Gao_VectorNet_Encoding_HD_Maps_and_Agent_Dynamics_From_Vectorized_Representation_CVPR_2020_paper.pdf).

---