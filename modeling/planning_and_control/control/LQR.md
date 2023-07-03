# LQR Control

Linear Quadratic Regulator (LQR) control is an optimal control strategy that is used to control linear dynamic systems. It leverages the principles of optimal control theory to calculate a control input that will drive the system to a desired state while minimizing a predefined cost function. This cost function is typically defined as the sum of the squares of both the system's states and control inputs, making the function quadratic.

The key advantage of LQR control is its balance between control effort and control accuracy. By adjusting the weights in the cost function, we can choose to prioritize either minimizing control effort (using as little energy or resources as possible) or minimizing the deviation from the desired state (trying to get the system as close as possible to a set point).

However, LQR assumes that the system it is controlling is perfectly linear, which is not always the case in real-world situations, and this can be a limitation of LQR. Extensions of LQR, such as Linear Quadratic Gaussian (LQG) control, are used when dealing with systems with uncertainty or noise.

---

#### Data-driven LQR control design
the paper link is [here](https://arxiv.org/pdf/1807.03263.pdf).

#### The Power of Linear Controllers in LQR Control
the paper link is [here](https://arxiv.org/pdf/2002.02574.pdf).