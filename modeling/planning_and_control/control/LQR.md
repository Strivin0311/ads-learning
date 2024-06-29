# Linear Quadratic Regulator Control
*Here're some resources about LQR Control*

Intros:
* Linear Quadratic Regulator (LQR) control is an optimal control strategy that is used to control linear dynamic systems. It leverages the principles of optimal control theory to calculate a control input that will drive the system to a desired state while minimizing a predefined cost function. This cost function is typically defined as the sum of the squares of both the system's states and control inputs, making the function quadratic.

* The key advantage of LQR control is its balance between control effort and control accuracy. By adjusting the weights in the cost function, we can choose to prioritize either minimizing control effort (using as little energy or resources as possible) or minimizing the deviation from the desired state (trying to get the system as close as possible to a set point).

* However, LQR assumes that the system it is controlling is perfectly linear, which is not always the case in real-world situations, and this can be a limitation of LQR. Extensions of LQR, such as Linear Quadratic Gaussian (LQG) control, are used when dealing with systems with uncertainty or noise.

---


#### The power of linear controllers in LQR control

paper link: [here](https://arxiv.org/pdf/2002.02574)

citation: 
```bibtex
@inproceedings{goel2022power,
  title={The power of linear controllers in LQR control},
  author={Goel, Gautam and Hassibi, Babak},
  booktitle={2022 IEEE 61st Conference on Decision and Control (CDC)},
  pages={6652--6657},
  year={2022},
  organization={IEEE}
}
```


#### Data-driven LQR control design

paper link: [here](https://arxiv.org/pdf/1807.03263)

citation: 
```bibtex
@article{da2018data,
  title={Data-driven LQR control design},
  author={da Silva, Gustavo R Gon{\c{c}}alves and Bazanella, Alexandre S and Lorenzini, Charles and Campestrini, Luciola},
  journal={IEEE control systems letters},
  volume={3},
  number={1},
  pages={180--185},
  year={2018},
  publisher={IEEE}
}
```