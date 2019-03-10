[//]: # (Image References)
[image_0]: img/Outcome.png

# Localization of mobile robot using Extended Kalman Filters

In this lab, we will be applying an **EKF ROS package** to localize the robot inside a Gazebo environment. In the end, we will be able to drive the robot around in simulation and observe the **Odom** and **EKF** trajectories.

To run this project in your local machine, you need *ROS Kinetic* and *Gazebo Version 7+*.

## Installation

#### Create a Catkin Workspace (Clone the repository)

```
$ git clone https://github.com/mlsdpk/ekf-localization.git
$ cd ekf-localization
$ catkin_make
```

If you find the dependencies error, please install the required dependencies as follows:

#### Install Package Dependencies

```
$ cd ekf-localization
$ source devel/setup.bash
$ rosdep -i install turtlebot_gazebo
$ rosdep -i install turtlebot_teleop
```

#### Perform a system Update/Upgrade

```
$ apt-get update
$ apt-get upgrade -y
```

#### Build the packages

```
$ catkin_make
$ source devel/setup.bash
```

## Launching the main file

```
$ roslaunch main main.launch
```

Now, you should see Gazebo and rviz launching. Please note that Gazebo might take up to 5 mins to launch if the turtlebot gazebo world is first time running on your local machine.

In the terminal, use the keyboard commands(u-i-o-j-k-l-m-,-.) and drive the robot around. The red trajectory represents the *Odom* path whereas the green trajectory represents the *EKF* path.

![alt text][image_0]

You can also use **rqt_multiplot** to visualize the unfiltered and filtered poses. **rqt_multiplot** is not installed by default in your system. You can install it as follows:

```
$ apt-get install ros-kinetic-rqt -y
$ apt-get install ros-kinetic-rqt-multiplot -y
$ apt-get install libqwt-dev -y
$ rm -rf ~/.config/ros.org/rqt_gui.ini
```

#### Running the rqt_multiplot package

```
$ rosrun rqt_multiplot rqt_multiplot
```
