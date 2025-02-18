# FW-max_pro
YUHESEN Omnidrectional UGV FW-max pro ros driver

![FW-max pro main2](https://github.com/RLmodel/FW-max_pro/assets/32663016/3f21714b-cbf3-4c4d-bbf2-54e0334751be)


<br/>

## tested environment

- ubuntu 22.04
- ROS2 Humble

<br/>

## dependencies

<br/>

```bash
sudo apt install ros-humble-nav-msgs
sudo apt install ros-humble-rqt-robot-steering
```

<br/>

## clone && build && launch

<br/>

- source ROS2 environment

```bash
source /opt/ros/humble/setup.bash
```

<br/>

- move to {workspace}/{source_folder}

```bash
cd ~/ros2_ws/src
```

<br/>

- clone packages

```bash
git clone https://github.com/RLmodel/FW-max_pro-2025.git
```

<br/>

- move to workspace

```bash
cd ~/ros2_ws
```

<br/>

- colcon build && source install folder

```bash
colcon build --packages-select --symlink-install yhs_can_interfaces
colcon build --packages-select --symlink-install yhs_can_control
source install/setup.bash
```

<br/>

- ip link up && set bitrate

```bash
sudo ip link set can0 up type can bitrate 500000
```

<br/>

- launch

```bash
ros2 launch yhs_can_control yhs_can_control.launch.py
```

<br/>

- cmd_vel control test

```bash
rqt_robot_steering
```

<br/>

## Debug

- check can connection

```bash
ifconfig -a | grep can
```
<br/>

- check can message

```bash
candump can0
```

<br/>







![YUHESEN _ FW max Demonstration of robot functions 0-49 screenshot](https://github.com/RLmodel/FW-max_pro/assets/32663016/e8e05522-ea13-4c7e-8565-f1382aeb61f7)

![YUHESEN _ FW max Demonstration of robot functions 2-21 screenshot](https://github.com/RLmodel/FW-max_pro/assets/32663016/d67d85ca-d82e-4e7c-8ec8-7a1a76e13c17)

![FW-max pro trans](https://github.com/RLmodel/FW-max_pro/assets/32663016/adf93b97-11a0-47a0-92b4-db3f30a9c3aa)
