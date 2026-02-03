# Installation instructions

The installation provided below is composed of 6 steps.   
Overall, you should be able to install the dependencies, and run the code within 20 minutes.   


### 1) Install Docker
If you do not have **Docker** installed on your machine, please find the complete set instructions available here:   
[Docker installation](https://docs.docker.com/engine/install/ubuntu/)

If you are on Linux Ubuntu, you can install it by running:  
```
sudo apt install gnome-terminal
sudo apt update
sudo apt install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
sudo tee /etc/apt/sources.list.d/docker.sources <<EOF
Types: deb
URIs: https://download.docker.com/linux/ubuntu
Suites: $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}")
Components: stable
Signed-By: /etc/apt/keyrings/docker.asc
EOF

sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

Confirm that your Docker installation is successful: 
```
sudo docker run hello-world
```
This will print:  
<img src="https://github.com/guobang494/Bluerov2-Simulation-with-docker-env/blob/main/Bluerov2-Simulation-with-docker-env/INSTALLATION/docker_hello_world.png" width=100% height=100%>
  
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





### Acknowledgements 
Reference https://github.com/HKPolyU-UAV/bluerov2/tree/huyang-backup
(Based on the reference, eight propellers were introduced: bluerov2 -heavy config.)





