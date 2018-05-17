# Title
Navigation of Solar Sail Satellites using neural networks

Abstract
The use of neural networks to optimize navigation on solar satellites and other lightweight spacecraft is a concept that shows substantial promise. This merges the lightweight chassis and time invariant solar wind propulsion which allow operation at far distances from Earth with a neural network to allow automated decision-making at distances too extreme to control from Earth. An object oriented navigation solver known as Astro.IQ was modified for the satellite in question and optimized. The modifications were successful and optimizations along several variables were able to improve calculation accuracy. We recommend further research into neural networks for navigation, especially as autonomous satellites become more common in future expeditions.

Introduction
Substantial research has been performed on the cube sat, a satellite that fits inside a 10cm cube, all instrumentation included. This platform is meant to serve as a modular framework that any space research agency can place instrumentation into and send up, and the small size ensures that multiple satellites can be deployed at once, getting more value out of each orbital launch.
Another technology being researched is the solar sail, where a satellite or vessel is propelled by a large panel that is deployed once out of orbit. This panel is pushed by solar wind much like a real sail is pushed by terrestrial wind.

Purpose and Research
The purpose of this project is to research improvements to the navigation and propulsion control systems for a solar sail that is fitted to a cube sat, an application for which the solar sail’s relative lack of power compared to chemical propellant is mitigated. Focus will be on making the vessels autonomous to enable long-range operations and mass-deployment.

Subjects, Methods, and Analysis
A prominent subject in autonomous vehicles is the use of neural networks. A neural network takes in the various types of sensor data available to the vehicle, analyzes it, and computes a set of course corrections to be taken.
Most neural networks utilize a combination of training sets, where the answer is known, allowing any inaccuracies in the decision-making code to be remedied, and guided learning where the network is fed data and guidelines on how to approach solving it. The combination is meant to make a neural network more capable of solving new input patterns on its own, which is important for satellites that will be deployed long distances from Earth.
Two pieces of software were used in this research project, both written by Christopher I Sprague. The main one focused on thus far is Astro.IQ, written in Python.
Astro.IQ uses an object oriented approach to cast a current state, a target state, and some number of trajectory states between, with bounds on how far the trajectory can deviate from “normal”.
Using a database of previous trajectories, the generated trajectories are evaluated and optimized for the best performance.
The network makes use of random walks in the evaluation of the trajectory sets, while also utilizing backpropagation to train the optimization process. This creates a multilayer perceptron used to select models going forward.
Once this code is properly running, a model for a CubeSat with the proper solar sail rigging can be generated and simulated in the network.

Results
Astro.IQ functioned as intended once libraries were loaded.
Trajectories were plotted and optimized with solar sail loaded as the satellite type.
Some optimization of the neural network was performed, using several different variables as the optimization bases.

Conclusions
Neural network learning is a very powerful tool for keeping autonomous spacecraft on course, especially when communication with Mission Control is limited.
Models in use are intended for use with low-mass low-propulsion systems, which makes them perfect for CubeSail satellites.
Highly feasible to use neural networks to guide CubeSail satellites as the technology of both satellite and software improves.

Directions for Future Research
Improvements to the neural network to better optimize route selection.
Research into automated state detection – If a satellite has a module added on last minute, or picks up samples/drops off a probe, be able to recalibrate the mass and/or surface as appropriate in calculations going forward.
