+++
title = "Word recognition on a micro controller"
date = "2021-06-24"

[extra]
subtitle = "Running neural networks on a micro controller"
date = "June 2021"
abstract = "Machine learning is traditionally very resource intensive. In this project, we made use of Tensorflow Lite to port small speech recognition models to an embedded computing device with highly constrained memory and cpu speed. The models can recognize and distinguish multiple English words."
+++

# About this Project
For our industrial project with ARM, we were tasked to build a speech recognition model and run it on a highly resource constrained micro controller.

To accomplish this task we had to collect training data, design a good but constrained neural network, and then train the neural network on the training data.

Once a network was trained, it was to be quantized, i.e. turned into a fixed-point representation, such that it can run in an adequate time and consume less memory on the micro controller.

Finally, we had to built and test a control code for the micro controller, which is a C program that includes the Tensorflow lite library, as well as facilities to load and run the model obtained in the previous step.

This program is also responsible for gathering input data from the sensors, as well as communicating the inference results back to the outside world.

Our final product packaged all of these pieces up into a GUI written in Python.

# My Contribution

- I leveraged grid search algorithms to determine good small model candidates and train them on our available data
- I wrote C routines to decode and load the model into Tensorflow Lite, as well as run the model on the micro controller and communicate with the sensors
- Collaborated intensively with my group members to integrate these parts of the process with a unified GUI written in Python

![](/image/portfolio/arduino.png)
The micro controller we used to run the neural network.
