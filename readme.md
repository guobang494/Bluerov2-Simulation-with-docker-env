## Installation 
## Reference https://github.com/HKPolyU-UAV/bluerov2/tree/huyang-backup
## Based on the reference, eight propellers were introduced: bluerov2 -heavy config.

### Software version:
* Python 3.7
* ROS ([ROS noetic](http://wiki.ros.org/noetic/Installation/Ubuntu) recommended)
* [uuv simulator](https://uuvsimulator.github.io/)
* [Acados](https://docs.acados.org/installation/index.html)


  
### 1) Install Docker
	https://docs.docker.com/engine/install/ubuntu/

### 2) Download the code
        mkdir -p  ~/catkin_ws
        cd ~/catkin_ws
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
      
       cd /root/catkin_ws/Bluerov2-Simulation-with-docker-env/src/bluerov2/bluerov2_dobmpc/scripts
       python3 generate_c_code.py
       cd /root/catkin_ws/Bluerov2-Simulation-with-docker-env
       catkin_make

### 4) Change the path 
	change this file 
	/root/catkin_ws/Bluerov2-Simulation-with-docker-env/src/bluerov2/bluerov2_dobmpc/config/gazebo_tank.yaml
	line 4   into 
	ref_traj: /root/catkin_ws/Bluerov2-Simulation-with-docker-env/src/bluerov2/bluerov2_dobmpc/traj/tank_dob.txt

   
### 5) set gazebo display(not in the docker )    
	open the other terminal 
	xhost +local:docker
   
### 6) launch the demo
	cd /root/catkin_ws/Bluerov2-Simulation-with-docker-env
	source ./devel/setup.bash
	roslaunch /root/catkin_ws/Bluerov2-Simulation-with-docker-env/src/bluerov2/bluerov2_dobmpc/launch/start_dobmpc_tank.launch






