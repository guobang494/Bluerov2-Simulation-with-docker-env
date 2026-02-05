# Simulation demo instructions
These instructions start a Gazebo demo to run the BlueROV2H controlled via MPC, simulated in the UCL Ocean Towing Tank.   
If you want to change the path senario, we provide further instructions in the ![Path scenario instructions](./Path_scenario_instructions.md/) file.

### 1) Start the container
Open a new terminal:
```
sudo docker start my_bluerov_container; sudo docker exec -it my_bluerov_container bash
```


### 2) Set gazebo display (not in the Docker)    
Leave the first terminal open, and open a new second terminal. In the second terminal, type:  
```
	xhost +local:docker
```
This allows the Docker to display content on the screen.  

### 3) Start the Gazebo demo
Start a demo lasting for 180 s, where the BlueRov2 follows a lemniscate path:
```
cd /root/catkin_ws/Bluerov2-Simulation-with-docker-env
source ./devel/setup.bash
roslaunch /root/catkin_ws/Bluerov2-Simulation-with-docker-env/src/bluerov2/bluerov2_dobmpc/launch/start_dobmpc_tank.launch
```
