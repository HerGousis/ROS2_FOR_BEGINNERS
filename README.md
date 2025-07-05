# ROS2 for Beginners

1.First we need to have Ubuntu 22.04 and the ROS2 22.04 version downloaded and I recommend that you also download Visual Studio Code. 

## 1o example
Controlling the turtle using the keyboard.
We open two terminals and write the commands:
 ```Shell
 ros2 run turtlesim turtlesim_node 

 ros2 run turtlesim turtle_teleop_key
```
respectively.
 
 Note: Ctrl+C stops executing commands.

  <div style="text-align:center;">
    <img src="/1.png" alt="1" width="800">
</div>

## Install colcon

open Terminal 
```
sudo apt update

 sudo apt install python3-colcon-common-extensions
```

## Autocompletion
```
 cd /usr/share/colcon_argcomplete/hook/

ls

 gedit ~/.bashrc  (Ανοιγει το αρχειο bashrc)
```
and I add this:
```
source /usr/share/colcon_argcomplete/hook/colcon-argcomplete.bash
```
and I activate it with

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
(and 4 build install log src folders will appear)
```
 cd install
 ls
```
(and I see setup.bash)
```
 cd
 source ~/ros2_ws/install/setup.bash 

 gedit ~/.bashrc  
```
(Opens the bashrc file)

and I add this:
```
source ~/ros2_ws/install/setup.bash
```
and I write in the terminal:

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
(and it should output my_robot_conroller)
we have Visual Studio Code

```
code .
``` 
(and opens the Visual code environment with the junk)
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
after
```
 cd ..
```
in here
```
hercules@hercules:~/ros2_ws$
```
```
 coclon build 
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
pip3 list | grep setuptools 
```
(I must have 58.2.0)
If I don't have it, I write:
```
pip3 install setuptools==58.2.0
pip3 list | grep setuptools
```
(to confirm if I have 58.2.0)
## my_first_node.py
At the terminal [hercules@hercules:~/ros2_ws$]

```
ros2 run my_robot_controller my_first_node
````

and I see the result:

<div style="text-align:center;">
    <img src="/2.png" alt="2" width="800">
</div>

## draw_circle.py
At the terminal [ hercules@hercules:~/ros2_ws$]
write :

```
colcon build --symlink-install
````

=>in another terminal I write:
(I open the turtle)

```
ros2 run turtlesim turtlesim_node
```

=> and in another terminal I write:

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
At the terminal (hercules@hercules:~/ros2_ws$ )
```
colcon build --install
source ~/.bashrc
ros2 run my_robot_controller pose_subscriber 
```
=> and in another terminal I write : (hercules@hercules:~$)
```
ros2 run turtlesim turtlesim_node
```
=> and in another terminal I write :
```
ros2 run my_robot_controller draw_circle
```
and I see in the 1st terminal (pose_subscriber) the x and y are constantly changing
## turtle_controller.py
At the terminal (hercules@hercules:~/ros2_ws$ )
```
colcon build --symlink-install
source ~/.bashrc
ros2 run my_robot_controller turtle_controller
clear
cd
source .bashrc (αν κανω καποια αλλαγη στον κωδικα )
ros2 run my_robot_controller turtle_controller
```
=>and in another terminal I write
```
ros2 run turtlesim turtlesim_node
```
=> and in another terminal I write :
```
ros2 run my_robot_controller pose_subscriber
```

<div style="text-align:center;">
    <img src="/4.png" alt="4" width="800">
</div>