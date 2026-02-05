# BlueROV2-Simulation-ROS-Qualisys
This repository contains the code to:  
  
a) **simulate a BlueROV2 Heavy** vehicle in a **Gazebo** environment resembling the University College London Ocean Towing tank;  
b) **control the BlueROV2 Heavy** in a laboratory environment, based on a **ROS (1) middleware**, and using the **Qualisys** motion capture tracking system.  

## Installation 
This software can be run in a **Docker container**, which we provide.
Detailed instructions on installation of the container and on environmental set-up are available within the ![INSTALLATION](./INSTALLATION/INSTALLATION.md/) file.    

In a nutshell, this software employs:  
* Python 3.7
* ROS ([ROS noetic](http://wiki.ros.org/noetic/Installation/Ubuntu) recommended)
* [uuv simulator](https://uuvsimulator.github.io/)
* [Acados](https://docs.acados.org/installation/index.html)

## Simulation 
Upon following the installation instructions, you will be able to run a control architecture composed of a Model Predictive Control in the virtual water tank.   
You will see the BlueROV2H vehicle as:  
<img src="https://github.com/guobang494/Bluerov2-Simulation-with-docker-env/blob/main/INSTALLATION/BlueROV2H_UCL_Ocean_Towing_Tank.png" width=100% height=100%>
  moving in a path such as in the following example:  
<img src="https://github.com/guobang494/Bluerov2-Simulation-with-docker-env/blob/main/INSTALLATION/Gazebo_animation.gif" width=100% height=100%>





  



