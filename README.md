#  Objects Arrangement Robot

__Objects Arrangement Robot Demo Video - [[YouTube]](https://youtu.be/xkUNAQp0_Gk)__
## Environment

* __Ubuntu 18.04__ 
* __ROS Melodic__
* __python 2.7__

***
## Installing

1. **Install ROS**

    Follow these [ROS Melodic installation instructions](http://wiki.ros.org/melodic/Installation).
    You can select any of the default configurations in step 1.4; even the
    ROS-Base (Bare Bones) package (`ros-melodic-ros-base`) is enough.

2. **Download the code**
    ```
    $ cd ~/catkin_ws/src
    $ git clone this repository 
    ```

3. **Install python dependencies**
    ```
    $ cd ~/catkin_ws/src/Parts-Arrangement-Robot
    $ pip install -r requirements.txt
    ```

4. **Install ROS dependencies**
    ```
    $ cd ~/catkin_ws
    $ rosdep install --from-paths src -i --rosdistro melodic
    $ sudo apt-get install ros-melodic-rosbash ros-melodic-ros-comm
    ```

5. **Build**
    ```
    $ cd ~/catkin_ws
    $ catkin_make
    ```
## Quick Start

* `$ roslaunch gripper_ur5 gazebo_env_setting.launch`
* `$ roslaunch gripper_ur5_moveit_config moveit_planning_execution.launch`
* `$ roslaunch yolov3_pytorch_ros detector.launch`
* `$ rosrun gripper_ur5 robot_sorting_yolo.py`


## The main filse to check are :

* /yolov3_pytorch_ros/src : These yolo detector  
* /gripper_ur5/src/robot_sorting_yolo.py : This is path planing script which take messages from yolo detector. 

## Node info - Launch

* __To simulate the robot environment launch the following:__
   
   ```
    $ roslaunch gripper_ur5 gazebo_env_setting.launch
    ```

* __For setting up the MoveIt! nodes to allow motion planning run:__
    
    ```
    $ roslaunch gripper_ur5_moveit_config moveit_planning_execution.launch`
    ```

* __Start screw grasp detection node:__
 
    ```
     $ roslaunch yolov3_pytorch_ros detector.launch
     ```


* __Start screw sorting robot node:__
    
    ```
    $ rosrun gripper_ur5 robot_sorting_yolo.py
    ```


 ## Reference:
 
 https://github.com/Kminseo/Parts-Arrangement-Robot.git
