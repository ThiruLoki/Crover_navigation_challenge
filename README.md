# Crover_navigation_challenge

## Software Requirements:

 This package was developed for ROS-Neotic. But should be compatible for other versions of ROS1.
 
## Installation:

1. Install ROS: Follow the link to install ROS in your Ubuntu system  $ http://wiki.ros.org/ROS/Installation


2. Install the packages by executing the following commands in your terminal:

3. Clone workspace

```sh
$ git clone https://github.com/ThiruLoki/Crover_navigation_challenge.git
```

4. Install robot_localization package.

$ sudo apt-get install ros-noetic-robot_localization.



$ cd Crover_navigation_challenge/

$ sudo rm -r build/
$ sudo rm -r devel/

$ catkin_make



4. Install the required dependencies

 $ rosdep install --from-paths src --ignore-src -y
 
5. Source the environment.

 $ source devel/setup.bash
```
