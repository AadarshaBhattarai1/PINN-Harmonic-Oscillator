# Physics-Informed Neural Networks (PINNs) for Damped Harmonic Motion
**Independent Research Project | Physics and Neural Network**

## Executive Summary
This project demonstrates the implementation of a Physics-Informed Neural Network (PINN) to solve the Ordinary Differential Equation (ODE) of a damped harmonic oscillator. As it implements PINN, this model is constrained by physical laws which allow it to learn about the motion of the oscillator without any labeled training data. Thus, it is different from standard deep learning in this regard. 


## Introduction (Physical Background)
The model is designed to satisfy the second-order linear ODE:
$$m\frac{d^2x}{dt^2} + \mu\frac{dx}{dt} + kx = 0$$

Where:
* **m = 1.0** ; Mass
* **k = 40.0** ; Spring Constant
* **μ = 0.5** ; Damping Coefficient

## Technical Methodology
* **Automatic Differentiation:** torch.autograd is used to calculate the 1st derivative (velocity) and 2nd derivative (acceleration) of the network's output with respect to time.
* **Loss Function:** A composite loss function is defined as: $Loss = Loss_{physics} + 100 \cdot Loss_{x0} + 10 \cdot Loss_{v0}$. This ensures that the model strictly adheres to the laws of motion and uses the initial conditions ($x=1, v=0$).
* **Optimization:** Trained for 10,000 iterations using the Adam optimizer ($lr=1e-3$).

## Results
The AI-predicted path (Red) perfectly aligns with the analytical mathematical solution (Blue), which proves that the neural network successfully estimated the correct physical behavior of the system.

![Final Results Plot](result_plot.png)

## Significance
I developed this project to explore application of computation in physics with an inspirational ambition of pursuing **AI for Science.** This project demonstrates that neural networks can be used as powerful solvers for complex differential equations of physics and engineering.

