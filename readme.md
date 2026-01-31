## Installation 
## Reference https://github.com/HKPolyU-UAV/bluerov2/tree/huyang-backup
## Based on the reference, eight propellers were introduced: bluerov2 -heavy config.

### Software version:
* Python 3.7
* ROS ([ROS noetic](http://wiki.ros.org/noetic/Installation/Ubuntu) recommended)
* [uuv simulator](https://uuvsimulator.github.io/)
* [Acados](https://docs.acados.org/installation/index.html)


  
### 1) Install Docker

### 2) Download the code
        mkdir -p  ~/catkin_ws/src
        cd ~/catkin_make/src
        git clone https://github.com/guobang494/Bluerov2-Simulation-with-docker-env

   
### 2) Install Docker Image
      docker pull zebangg/ros1_noetic_bluerov2:v2
      docker run -it \
          --name my_bluerov_container \
          --network host \
          --privileged \
          -v /tmp/.X11-unix:/tmp/.X11-unix \
          -v ~/catkin_ws:/root/catkin_ws \
          -e DISPLAY=$DISPLAY \
          zebangg/ros1_noetic_bluerov2:v2 \
          bash
  
### 3) Catkin_make
       cd 


