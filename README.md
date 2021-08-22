# Crover_navigation_challenge

## Software Requirements:

 This package was developed for ROS-Neotic. But should be compatible for other versions of ROS1.
 
## Installation:

 ROS Installation: Follow the link to install ROS in your Ubuntu system  $ http://wiki.ros.org/ROS/Installation


Install the packages by executing the following commands in your terminal:

3. Clone workspace 

```sh
$ git clone https://github.com/ThiruLoki/Crover_navigation_challenge.git
```

4. Install robot_localization package.
```sh
$ sudo apt-get install ros-noetic-robot-localization 
```
or clone from github repo
```sh
$ https://github.com/ros-planning/navigation.git
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
9. Install robot_localization package
 The robot_localization is a ROS package for nonlinear state estimation nodes.
 Requires "geographic-msgs". If not installed:

 ```sh
 sudo apt-get install ros-noetic-geographic-msgs
 ```
10. Source the environment.
```sh
 $ source devel/setup.bash
```


## How to run it?

Run the launch files by entering the bewlow command
```sh
$roslaunch extended_kalman_filter_pkg task.launch 
```
The above command launches all nodes along with the Rviz, this will take /sensor/odom/gorund_truth and /odometry/filtered topic data as input and gives "output.bag" as the output to get the estimated position and orientation of the car. The output is saved in bag_files folder inside the extended_kalman_filter package.



The above .gif shows the Rviz visualization.

## Techincal Description

The localization and sensor fusion is most important step for any autonomous vechicles/robots. Here I used Extended kalman filter for noise mitigation, it use recursive Bayesian filtering where the noise in the system is assumed Gaussian due to many unkuwn and uncontrolable factor due to which this noise come in our system. As system is non-linear system so in place of kalman filter i used extender kalmen filter to enconter non-linearty in system, where non-linearity are approximated using the first or second order derivative for state update and the covariance update. The robot_localization package $http://docs.ros.org/en/noetic/api/robot_localization/html/index.html is used to estimate the position and orientation of the car. 

## INPUT
The input .bag file is given to the ekf_localization node in the form of "data.bag".(stored in the bag_files folder). The sensor inputs /sensors/gnss/odom + /sensor/odom from the ROS Topics are fused to get the state estimation of the car. To get the filtered odometry data, the EKF is applied in basis of given parameter stored in the params folder of the extended_kalman_filter package.
## OUTPUT
The output is stored in form of .bag file in bag_files folder of extended_kalman_filter package. To examine the output use rosbag info and rosbag play in the terminal.
```sh
rosbag info output.bag
```
```sh
rosbag play output.bag
```
## PERFORMANCE ANALYSIS


The output obtained from the extended kalman filter is satisfying. The below graphical image shows the performance of EKF in Rviz visualization.

![Alt Text](https://github.com/ThiruLoki/Crover_navigation_challenge/blob/master/My_task_crover_ws/ekf.gif)

![image](https://github.com/ThiruLoki/Crover_navigation_challenge/blob/master/My_task_crover_ws/position.png)
The above image shows the position of the car. (in circles)

![image](https://github.com/ThiruLoki/Crover_navigation_challenge/blob/master/My_task_crover_ws/orientation.png). 
The above image show the orientation of the car (in arrows)

![image](https://github.com/ThiruLoki/Crover_navigation_challenge/blob/master/My_task_crover_ws/performance.png)
The above image shows the output of rqt_plot.

## WORK DESCRIPTION

* After understanding the problem statement, I gathered the things which i know before and started refering to the online tutorials & reading forums related to the task.
* Gone through various packages namely Autoware $ https://github.com/Autoware-AI/autoware.ai etc, and finaly chosen robot_localization package $ http://docs.ros.org/en/noetic/api/robot_localization/html/index.html
* The reason for choosing the robot_localization packages is the time constrain of the task.
* Then I started working on by making ROS packages, writing launch files, setting parameters and much more.
* I've used Rqt_plots to analyze the filterd output and i analyzed the nodes and topics by using rqt_graphs.
* Finally i have successfully implemented the extended kalaman filter and obtained state estimation (both position and orientation) of the car.
* Looking forward to work and develop new alogorithms with the crover team, once again thanks for the opportunity.
