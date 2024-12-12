# ROS2 ��� ���������

1.������ �� ������ �� ������ Ubuntu 22.04 ��� ��� ������ ROS2 22.04 ����������� ��� ������� �� ���������� ��� �� Visual Studio Code. 

## 1o ���������� 
��������� ��� ������� ���� ��� �������������.
 ��������� ��� terminal ��� ��� �������� ��� ������� :

1. ros2 run turtlesim turtlesim_node 

2. ros2 run turtlesim turtle_teleop_key

 ����������.
 
 ��������: ��  Ctrl+C ��������� �� ����������� �� ������� 

  <div style="text-align:center;">
    <img src="/1.png" alt="1" width="800">
</div>

## Install colcon

��������� Terminal 

1. sudo apt update

2. sudo apt install python3-colcon-common-extensions

## Autocompletion

1. cd /usr/share/colcon_argcomplete/hook/

2. ls

3. gedit ~/.bashrc  (������� �� ������ bashrc)

��� ���������� ���� :

4. source /usr/share/colcon_argcomplete/hook/colcon-argcomplete.bash

��� �� ���� �� 

5. source .bashrc

## Create ROS2 Workspace

1. source ~/.bashrc
2. ls
3. mkdir ros2_ws
4. cd ros2_ws
5. ls
6. mkdir src
7. ls 
8. colcon build
9. ls

(��� �� ����������� 4 ������� build install log src)

10. cd install
11. ls

(��� ����� �� setup.bash)

12. cd
13. source ~/ros2_ws/install/setup.bash 

14. gedit ~/.bashrc  

(������� �� ������ bashrc)

��� ���������� ���� :

15 .source ~/ros2_ws/install/setup.bash

��� ����� ��� terminal :

16. source .bashrc

##   Create ROS2 package
1. cd ros2_ws/
2. cd src
3. ls
4. ros2 pkg create my_robot_controller --build-type ament_python --dependencies rclpy

5. ls

(��� ������ �� ������ my_robot_conroller)
����� ������ �� Visual Studio  Code

6. code .  (��� ������� �� ���������� ��� Visual code �� �� ������)

7. my_robot_controller
8. __init__.py
9. resource
10. my_robot_controller
11. test
12. package.xml
13. setup.cfg
14. setup.py

���  ���� 

15. cd ..

���� ��� 
hercules@hercules:~/ros2_ws$

16. coclon build ( �� ������ ���� �������� �� ���� �� ���� ���������**)
 
17. ls 
18. cd install
19. ls
20. cd ..
21. cd ..
22. pwd


 ** 1.  sudo apt install python3-pip
2. pip3 list
3. pip3 list | grep setuptools (������ �� ��� 58.2.0)

�� ��� ��� ��� ����� :
1. pip3 install setuptools==58.2.0
2. pip3 list | grep setuptools (��� �� ����������� �� ��� �� 58.2.0)

## my_first_node.py
�� ��������� [hercules@hercules:~/ros2_ws$]

1. ros2 run my_robot_controller my_first_node

��� ����� �� ���������� :

<div style="text-align:center;">
    <img src="/2.png" alt="2" width="800">
</div>

## draw_circle.py
�� ��������� ��� ���� ���� [ hercules@hercules:~/ros2_ws$]
����� :
1. colcon build --symlink-install

=>  �� ���� ��������� ����� :
(������ ��� ������ )

2. ros2 run turtlesim turtlesim_node


=> ��� �� ���� ��������� ����� :

3. source .bashrc

4. ros2 run my_robot_controller draw_circle

<div style="text-align:center;">
    <img src="/3.png" alt="3" width="800">
</div>

## Pose_subscriber.py 
�� ��������� ��� ���� ���� (hercules@hercules:~/ros2_ws$ )
1. colcon build --install
2. source ~/.bashrc
3. ros2 run my_robot_controller pose_subscriber 

=> ��� �� ���� terminal ����� : (hercules@hercules:~$)
4. ros2 run turtlesim turtlesim_node
=> ��� �� ���� terminal ����� :
5. ros2 run my_robot_controller draw_circle

��� ����� ��� 1� terminal (pose_subscriber) �� � ��� �� y �� �������� ������� 

## turtle_controller.py
�� ��������� ��� ���� ���� (hercules@hercules:~/ros2_ws$ )
1. colcon build --symlink-install
2. source ~/.bashrc
3. ros2 run my_robot_controller turtle_controller
4. clear
5. cd
6. source .bashrc (�� ���� ������ ������ ���� ������ )
7. ros2 run my_robot_controller turtle_controller

=>��� �� ���� terminal 
8. ros2 run turtlesim turtlesim_node

=> ��� �� ���� terminal ����� :
9. ros2 run my_robot_controller pose_subscriber

<div style="text-align:center;">
    <img src="/4.png" alt="4" width="800">
</div>