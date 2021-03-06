**DEPRECATED: THIS REPOSITORY IS NO LONGER MAINTAINED**

Please check out [Y-modify/deepl2](https://github.com/Y-modify/deepl2)

# deepl2-ros-gazebo
[![license](https://img.shields.io/github/license/Y-modify/deepl2-ros-gazebo.svg)](LICENSE)

An experiment to make [YamaX](https://www.y-modify.org/yamax) walk in the simulation environment using ROS and Gazebo.

DeepL2 Project: [https://blog.y-modify.org/2018/01/04/deepl2-start/](https://blog.y-modify.org/2018/01/04/deepl2-start/)


# Get started
```shell
docker-compose up -d
```
then connect to localhost:5900 using VNC

## Setup

```shell
. /opt/ros/lunar/setup.sh
. devel/setup.sh
```


### Launch a simurator and controllers
```shell
roslaunch yamax_gazebo world.launch # gui:=true headless:=false if you need gui
```
Now you can control joints by publishing to `/yamax/{joint_name}_position_controller/command`

###### Example:
```shell
rostopic pub /yamax/neck_position_controller/command std_msgs/Float64 1.57
```
Will turn the head to 90°

### Launch controllers
```shell
roslaunch yamax_control yamax_control.launch
```

### Rviz
You need `urdf_tutorial` package if you don't have rviz config file(.rviz)
```shell
roslaunch yamax_description display.launch
```
