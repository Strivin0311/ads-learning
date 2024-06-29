# ADS Testing Oracle
*Here're some resources about ADS Testing Oracle*


Intros:
* ADS testing oracle is a concept borrowed from software testing, which refers to a mechanism or method that determines whether a system under test is behaving as expected for a given set of inputs and conditions. In other words, the oracle gives us the "right answer" against which the system's actual output can be compared.

* In ADS testing, an oracle might take the form of a predefined set of rules or behaviors that an autonomous vehicle is expected to follow in response to specific inputs or situations. For example, given a scenario where a pedestrian is crossing the street, the oracle might define that the expected behavior of the ADS is to slow down and stop until the pedestrian has crossed.

* Creating an accurate and reliable oracle for ADS testing can be a complex task, given the vast number of potential scenarios an autonomous vehicle might encounter, and the often unpredictable nature of real-world driving conditions. The oracle must accurately reflect legal and safe driving practices, and be robust enough to handle a wide variety of inputs and situations.

* There are several approaches to creating oracles for ADS testing. Some methods rely on the use of expert knowledge to define expected behaviors, while others may use machine learning techniques to learn from real-world driving data. Additionally, "pseudo-oracle" methods can be used, where the ADS's behavior is compared to that of a human driver in the same scenario. However, these methods have their limitations and can introduce their own challenges, such as the potential for human error or bias.

* Ultimately, the goal of an oracle in ADS testing is to provide a reliable means of validating the performance of an autonomous driving system, helping to ensure its safety and reliability before it is deployed on public roads.

---

### Safety Standard

#### Overview of the 2nd Edition of ISO 26262- Functional Safety – Road Vehicles
slides link: [here](https://pan.baidu.com/s/1Bts8V2xlcCg_CKHkf-KQow), with the extraction code `7tof`

#### ISO 26262- Functional Safety Standard for Modern Road Vehicles
article link: [here](https://pan.baidu.com/s/1OJ6N82aWSiaLWonxVozvDw), with the extraction code `bntu`

#### ISO26262 1-12 EN
reference link: [here](https://pan.baidu.com/s/1IFR_SuBgH83f-9N37d-UoA), with the extraction code `zmp4`


### Safety Metrics

#### Quality metrics and oracles for autonomous vehicles testing

paper link: [here](https://tsigalko18.github.io/assets/pdf/2021-Jahangirova-ICST.pdf)

citation: 
```bibtex
@inproceedings{jahangirova2021quality,
  title={Quality metrics and oracles for autonomous vehicles testing},
  author={Jahangirova, Gunel and Stocco, Andrea and Tonella, Paolo},
  booktitle={2021 14th IEEE conference on software testing, verification and validation (ICST)},
  pages={194--204},
  year={2021},
  organization={IEEE}
}
```

#### Model predictive instantaneous safety metric for evaluation of automated driving systems

paper link: [here](https://arxiv.org/pdf/2005.09999)

citation: 
```bibtex
@inproceedings{weng2020model,
  title={Model predictive instantaneous safety metric for evaluation of automated driving systems},
  author={Weng, Bowen and Rao, Sughosh J and Deosthale, Eeshan and Schnelle, Scott and Barickman, Frank},
  booktitle={2020 IEEE Intelligent Vehicles Symposium (IV)},
  pages={1899--1906},
  year={2020},
  organization={IEEE}
}
```

### Modular Metrics

#### Let-3d-ap: Longitudinal error tolerant 3d average precision for camera-only 3d detection

paper link: [here](https://arxiv.org/pdf/2206.07705)

citation: 
```bibtex
@article{hung2022let,
  title={Let-3d-ap: Longitudinal error tolerant 3d average precision for camera-only 3d detection},
  author={Hung, Wei-Chih and Kretzschmar, Henrik and Casser, Vincent and Hwang, Jyh-Jing and Anguelov, Dragomir},
  journal={arXiv preprint arXiv:2206.07705},
  year={2022}
}
```
    