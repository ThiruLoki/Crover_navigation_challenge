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
```sh
$ sudo apt-get install ros-noetic-robot_localization.
```
5. Navigate to the working directory
```sh
$ cd Crover_navigation_challenge/
```
6. Remove both build and devel folders before catkin_make to avoid make errors.
```sh
$ sudo rm -r build/
```
```sh
$ sudo rm -r devel/
```
7. Build the code into the workspace
```sh
$ catkin_make
```
8. Install the required dependencies
```sh
 $ rosdep install --from-paths src --ignore-src -y
 ```
 
9. Source the environment.
```sh
 $ source devel/setup.bash
```
## Install Ros navigation stack
```sh
$ https://github.com/ros-planning/navigation.git
```

## Running the command
