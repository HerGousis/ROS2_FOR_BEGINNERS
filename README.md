# ROS2 ��� ���������

1.������ �� ������ �� ������ Ubuntu 22.04 ��� ��� ������ ROS2 22.04 ����������� ��� ������� �� ���������� ��� �� Visual Studio Code. 

## 1o ���������� 
��������� ��� ������� ���� ��� �������������.
 ��������� ��� terminal ��� ��� �������� ��� ������� :
 ```Shell
 ros2 run turtlesim turtlesim_node 

 ros2 run turtlesim turtle_teleop_key
```
 ����������.
 
 ��������: ��  Ctrl+C ��������� �� ����������� �� ������� 

  <div style="text-align:center;">
    <img src="/1.png" alt="1" width="800">
</div>

## Install colcon

��������� Terminal 
```
sudo apt update

 sudo apt install python3-colcon-common-extensions
```

## Autocompletion
```
 cd /usr/share/colcon_argcomplete/hook/

ls

 gedit ~/.bashrc  (������� �� ������ bashrc)
```
��� ���������� ���� :
```
source /usr/share/colcon_argcomplete/hook/colcon-argcomplete.bash
```
��� �� ���� �� 

```
source .bashrc
```
## Create ROS2 Workspace

```
source ~/.bashrc
 ls
 mkdir ros2_ws
 cd ros2_ws
 ls
 mkdir src
 ls 
 colcon build
 ls
```
(��� �� ����������� 4 ������� build install log src)
```
 cd install
 ls
```
(��� ����� �� setup.bash)
```
 cd
 source ~/ros2_ws/install/setup.bash 

 gedit ~/.bashrc  
```
(������� �� ������ bashrc)

��� ���������� ���� :
```
source ~/ros2_ws/install/setup.bash
```
��� ����� ��� terminal :

```
source .bashrc
```
##   Create ROS2 package
```
cd ros2_ws/
cd src
ls
ros2 pkg create my_robot_controller --build-type ament_python --dependencies rclpy
```
```
ls
```
(��� ������ �� ������ my_robot_conroller)
����� ������ �� Visual Studio  Code

```
code .
``` 
(��� ������� �� ���������� ��� Visual code �� �� ������)
```
my_robot_controller
 __init__.py
 resource
 my_robot_controller
 test
 package.xml
 setup.cfg
 setup.py
```
���  ���� 
```
 cd ..
```
���� ��� 
```
hercules@hercules:~/ros2_ws$
```
```
 coclon build ( �� ������ ���� �������� �� ���� �� ���� ���������**)
```
```
 ls 
 cd install
 ls
 cd ..
 cd ..
 pwd
```

 ** 1.  sudo apt install python3-pip
 ```
pip3 list
pip3 list | grep setuptools (������ �� ��� 58.2.0)
```
�� ��� ��� ��� ����� :
```
pip3 install setuptools==58.2.0
pip3 list | grep setuptools (��� �� ����������� �� ��� �� 58.2.0)
```
## my_first_node.py
�� ��������� [hercules@hercules:~/ros2_ws$]

```
ros2 run my_robot_controller my_first_node
````

��� ����� �� ���������� :

<div style="text-align:center;">
    <img src="/2.png" alt="2" width="800">
</div>

## draw_circle.py
�� ��������� ��� ���� ���� [ hercules@hercules:~/ros2_ws$]
����� :

```
colcon build --symlink-install
````

=>  �� ���� ��������� ����� :
(������ ��� ������ )

```
ros2 run turtlesim turtlesim_node
```

=> ��� �� ���� ��������� ����� :

```
source .bashrc
````

```
ros2 run my_robot_controller draw_circle

```
<div style="text-align:center;">
    <img src="/3.png" alt="3" width="800">
</div>

## Pose_subscriber.py 
�� ��������� ��� ���� ���� (hercules@hercules:~/ros2_ws$ )
```
colcon build --install
source ~/.bashrc
ros2 run my_robot_controller pose_subscriber 
```
=> ��� �� ���� terminal ����� : (hercules@hercules:~$)
```
ros2 run turtlesim turtlesim_node
```
=> ��� �� ���� terminal ����� :
```
ros2 run my_robot_controller draw_circle
```
��� ����� ��� 1� terminal (pose_subscriber) �� � ��� �� y �� �������� ������� 

## turtle_controller.py
�� ��������� ��� ���� ���� (hercules@hercules:~/ros2_ws$ )
```
colcon build --symlink-install
source ~/.bashrc
ros2 run my_robot_controller turtle_controller
clear
cd
source .bashrc (�� ���� ������ ������ ���� ������ )
ros2 run my_robot_controller turtle_controller
```
=>��� �� ���� terminal 
```
ros2 run turtlesim turtlesim_node
```
=> ��� �� ���� terminal ����� :
```
ros2 run my_robot_controller pose_subscriber
```

<div style="text-align:center;">
    <img src="/4.png" alt="4" width="800">
</div>