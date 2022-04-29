# TinyDronet:      
### A Framework For Efficient Deployment of Lightweight Neural Network Models for Real-Time Drone Navigation


![alt text](https://github.com/aidins1/TinyDronet/blob/main/eehpc.png)


## UMBC Energy Efficient High Performance Computing Lab
 **Supervisior:** Dr Tinoosh Mohsenin tinoosh@umbc.edu
 
 **Author:** Aidin Shiri aidin.shiri@umbc.edu



## Datasets and Software Simulation Codes
Two datasets are used for training a neural network model which produce proper output for obstacle avoidance and steering task based on raw gray scale image inputs from drone camera. First [Dronet: Learning to fly by drivin](https://rpg.ifi.uzh.ch/dronet.html) dataset, which is collection of nearly 32K images which are annotated with collision/no-collision labels. We used this dataset to train a model which learns to perform the obstacle avoidance task, during the drone navigation. Secondly, the [Udacity's projects](https://www.udacity.com/course/self-driving-car-engineer-nanodegree--nd0013) dataset, which contains 70K images, captured from a camera mounted on a car with images captured left, right, and center view while driving. We used this dataset for learning the steering task to our model.

<img src="https://github.com/aidins1/TinyDronet/blob/main/dataset.png" width=50% height=50%>


## Implementation on a Server and GAP8 IoT Edge Device
For implementation of autonomous drone navigation application, we used CrazyFlie 2.0, an open source flying development instrument with AI-Deck extension board. The AI-Deck features a low power camera, Wi-Fi module and ultra low power RISC-V processor GAP8 which lets CrazyFlie to do on-board processing. Gray scale images captured from the drone camera is resized to 200x200 to feed to NN models either on-board or on the cloud.



<img src="https://github.com/aidins1/TinyDronet/blob/main/Crazyflie.jpg" width=30% height=30%>  <img src="https://github.com/aidins1/TinyDronet/blob/main/AI-Deck.jpg" width=30% height=30%>


In general, the neural network inference model of the drone perception can be performed by streaming image to a server and the inference output back to the drone, or by implementing the model on the edge. For this purpose, we implemented our model on a laptop as server implementation and GAP8 IoT device for the edge implementation. Detailed instructions and codes that we used in our experiments could be find in the links below:

[Server Implementation](https://github.com/GriffinBonner/ai-deck_obs_native)

[Edge Implementation](https://github.com/aurxenon/AIdeckTestbed)




## Power Measurment
To evaluate the energy efficiency and power consumption of our model on an edge devices, we implement it on  GAP8 IoT processor. GAP8 processor has a tiny fabric controller with 8 cluster cores for parallelization, which can be run at maximum frequency of 150MHz. We configured the device to achieve maximum performance and measured the models implementation results. Figure below shows the setup for measuring power consumption of GAP8 when the neural network model is running on-board. We used INA 219 module along with an Arduino Nano board  to monitor power consumption rate. 


<img src="https://github.com/aidins1/TinyDronet/blob/main/Measurement.jpg" width=50% height=50%>
