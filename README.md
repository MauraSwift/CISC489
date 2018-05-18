# Navigation of Solar Sail Satellites Using Neural Networks

## Abstract
The use of neural networks to optimize navigation on solar satellites and other lightweight spacecraft is a concept that shows substantial promise. This merges the lightweight chassis and time invariant solar wind propulsion which allows operation at far distances from Earth with a neural network to allow automated decision-making at distances too extreme to control from Earth. This project was inspired by an object oriented navigation solver known as Astro.IQ. A deep neural network from Google's machine learning crash course was modified to predict control variables based on a spacecraft's mass, position, and velocity. Three different optimizers were tested and it was found that in most cases the Adam Optimizer resulted in the best error reduction. We recommend further research into neural networks for navigation, especially as autonomous satellites become more common in future expeditions.

## Introduction
Substantial research has been performed on the cube sat, a satellite that fits inside a 10cm cube, all instrumentation included. This platform is meant to serve as a modular framework that any space research agency can place instrumentation into and send up, and the small size ensures that multiple satellites can be deployed at once, getting more value out of each orbital launch.
Another technology being researched is the solar sail, where a satellite or vessel is propelled by a large panel that is deployed once out of orbit. This panel is pushed by solar wind much like a real sail is pushed by terrestrial wind.

## Purpose and Research
The purpose of this project is to research improvements to the navigation and propulsion control systems for a solar sail that is fitted to a cube sat, an application for which the solar sail’s relative lack of power compared to chemical propellant is mitigated. Focus will be on making the vessels autonomous to enable long-range operations and mass-deployment.

## Subjects, Methods, and Analysis
A prominent subject in autonomous vehicles is the use of neural networks. A neural network takes in the various types of sensor data available to the vehicle, analyzes it, and computes a set of course corrections to be taken.
Most neural networks utilize a combination of training sets, where the answer is known, allowing any inaccuracies in the decision-making code to be remedied, and guided learning where the network is fed data and guidelines on how to approach solving it. The combination is meant to make a neural network more capable of solving new input patterns on its own, which is important for satellites that will be deployed long distances from Earth.

Two pieces of software were inspired this research project, both written by Christopher I Sprague. They are called Astro.IQ and Act.ai, and both are written in a combination of python and ipython notebooks. They both use neural networks to determine trajectory control variables, but Astro.IQ focuses on a simple Mars lander while Act.ai is meant to be used for interplanetary missions. Using a database of previous trajectories, the generated trajectories are evaluated and optimized for the best performance. The network makes use of random walks in the evaluation of the trajectory sets, while also utilizing backpropagation to train the optimization process. This creates a multilayer perceptron used to select models going forward.

Due to various difficulties including loading libraries, these pieces of software were not directly utilized, but a dataset from Act.ai was used. A deep neural network from Google's machine learning crash course was modified to be used on this data in order to predict control variables. The spacecraft mass, position, and velocity were mapped to the magnitude and direction of the control action. Three different optimizers were used - Gradient Descent, Adagrad, and Adam - to determine which one worked best for this dataset.

## Results
Plot of root mean squared error (RMSE) versus training time for the magnitude of the control action
![predicting u](https://user-images.githubusercontent.com/32310752/40210100-18036840-5a11-11e8-9de8-93a37304bd49.PNG)

Plot of RMSE versus training time for the x-coordinate of the control action
![predicting ux](https://user-images.githubusercontent.com/32310752/40210102-181931c0-5a11-11e8-8d84-c6212761997a.PNG)

Plot of RMSE versus training time for the y-coordinate of the control action
![predicting uy](https://user-images.githubusercontent.com/32310752/40210103-182dc6f8-5a11-11e8-8985-ad45f5139095.PNG)

Plot of RMSE versus training time for the z-coordinate of the control action
![predicting uz](https://user-images.githubusercontent.com/32310752/40210104-1841326a-5a11-11e8-9381-9344623d265f.PNG)

For the magnitude and x- and y-components of the control action, the Adam optimizer clearly produced the best results, and for the z-component the Adam and Gradient Descent optimizers performed equally well.

## Conclusions
Neural network learning is a very powerful tool for keeping autonomous spacecraft on course, especially when communication with Mission Control is limited.

Adam optimizer is the best choice of the optimizers considered for this type of data

Models in use are intended for use with low-mass low-propulsion systems, which makes them perfect for CubeSail satellites.

Highly feasible to use neural networks to guide CubeSail satellites as the technology of both satellite and software improves.

## Directions for Future Research
Improvements to the neural network to better optimize route selection.

Research into automated state detection – If a satellite has a module added on last minute, or picks up samples/drops off a probe, be able to recalibrate the mass and/or surface as appropriate in calculations going forward.
