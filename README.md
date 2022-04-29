# TinyDronet:      
### A Framework For Efficient Deployment of Lightweight Neural Network Models for Real-Time Drone Navigation


![alt text](https://github.com/aidins1/TinyDronet/blob/main/eehpc.png)


# UMBC Energy Efficient High Performance Computing Lab
### Faculty: Tinoosh Mohsenin tinoosh@umbc.edu
### Author: Aidin Shiri aidin.shiri@umbc.edu



# Datasets and Software Simulation Codes


# Implementation on GAP8 IoT Edge Device
For implementation of autonomous drone navigation application, we used CrazyFlie 2.0, an open source flying development instrument with AI-Deck extension board. The AI-Deck features a low power camera, Wi-Fi module and ultra low power RISC-V processor GAP8 which lets CrazyFlie to do on-board processing. Gray scale images captured from the drone camera is resized to 200x200 to feed to NN models either on-board or on the cloud.







# Power Measurment
To evaluate the energy efficiency and power consumption of our model on an edge devices, we implement it on  GAP8 IoT processor. GAP8 processor has a tiny fabric controller with 8 cluster cores for parallelization, which can be run at maximum frequency of 150MHz. We configured the device to achieve maximum performance and measured the models implementation results. Figure below shows the setup for measuring power consumption of GAP8 when the neural network model is running on-board. We used INA 219 module along with an Arduino Nano board  to monitor power consumption rate. 


<img src="https://github.com/aidins1/TinyDronet/blob/main/Measurement.jpg" width=50% height=50%>
