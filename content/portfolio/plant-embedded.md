+++
title = "Device to Monitor Plant Water Levels"
date = "2021-02-24"

[extra]
subtitle = "We designed and built a device to monitor plants water levels"
date = "February 2021"
link = "https://stacezwu.github.io/embedded-web/"
abstract = "Keeping plants hydrated is very important, but it can be easy to forgot to water a plant regularly. To assist with this, my team built a display to indicate water levels, powered by a raspberry pi, as well as a web interface which receives data from the device via MQTT."
+++

# About the project
For this project we conceptualized, designed, and implemented an embedded device to monitor plants at home. This works by tracking the water level of plants over time (taking into account the humidity and other environmental factors), to calculate when the plant should next be watered.

To notify the users of the need to water, we built a physical gauge that can be placed next to the plant, a button to indicate that it has been watered, as well as a web service to check on your plants on the go.

# What I did

I implemented communication with different sensors to measure humidity and Co2 concentration.

This was achieved by studying the sensors datasheets and then implementing their protocols in Python to address the sensors which were connected via the GPIO headers of a raspberry pi.

In a similar way, I also implemented controls for registering the button click, and controlling a stepper motor to move the gauge.

To display the water level, I built a physical gauge and connected it to the motor.

Finally to build the web interface I set up a python based web server. This server responds to HTTP requests, and receives updates from our device via the MQTT protocol. I also implemented the MQTT protocol on the device side to send updates, and set up a local MQTT broker to allow for real time communication between both parts.

<!-- ![](/image/portfolio/plant.png) -->
<center>
<iframe width="560" height="315" src="https://www.youtube.com/embed/3bfmrBaaDI8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</center>
