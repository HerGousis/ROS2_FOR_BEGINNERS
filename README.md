# ROS2 για Αρχάριους

1.Αρχικα θα πρεπει να εχουμε Ubuntu 22.04 και την εκδοση ROS2 22.04 κατεβασμενα και συνιστω να κατεβασετε και το Visual Studio Code. 

## 1o Παραδειγμα 
Χειρισμος της χελωνας μεσω του πληκτρολογιου.
 Ανοιγουμε δυο terminal και στο γραφουμε τις εντολες :
 ```Shell
 ros2 run turtlesim turtlesim_node 

 ros2 run turtlesim turtle_teleop_key
```
 αντιστοιχα.
 
 Σημειωση: Με  Ctrl+C σταματουν να εκτελουνται οι εντολες 

  <div style="text-align:center;">
    <img src="/1.png" alt="1" width="800">
</div>

## Install colcon

Ανοιγουμε Terminal 
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
και συμπληρωνω αυτο :
```
source /usr/share/colcon_argcomplete/hook/colcon-argcomplete.bash
```
και το καλω με 

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
(και θα εμφανιστουν 4 φακελοι build install log src)
```
 cd install
 ls
```
(και βλεπω το setup.bash)
```
 cd
 source ~/ros2_ws/install/setup.bash 

 gedit ~/.bashrc  
```
(Ανοιγει το αρχειο bashrc)

και συμπληρωνω αυτο :
```
source ~/ros2_ws/install/setup.bash
```
και γραφω στο terminal :

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
(και πρεπει να βγαζει my_robot_conroller)
εμεις εχουμε το Visual Studio  Code

```
code .
``` 
(και ανοιγει το περιβαλλον του Visual code με τα αχρεια)
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
και  μετα 
```
 cd ..
```
παμε εδω 
```
hercules@hercules:~/ros2_ws$
```
```
 coclon build ( αν βγαζει θεμα γραφουμε τα εξης σε αλλο τερματικο**)
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
pip3 list | grep setuptools (πρεπει να εχω 58.2.0)
```
Αν δεν την εχω γραφω :
```
pip3 install setuptools==58.2.0
pip3 list | grep setuptools (για να επιβεβαιωσω αν εχω τν 58.2.0)
```
## my_first_node.py
Σε τερματικο [hercules@hercules:~/ros2_ws$]

```
ros2 run my_robot_controller my_first_node
````

και βλεπω το αποτελεσμα :

<div style="text-align:center;">
    <img src="/2.png" alt="2" width="800">
</div>

## draw_circle.py
Σε τερματικο και στην θεση [ hercules@hercules:~/ros2_ws$]
γραφω :

```
colcon build --symlink-install
````

=>  σε αλλο τερματικο γραφω :
(ανοιγω την χελωνα )

```
ros2 run turtlesim turtlesim_node
```

=> και σε αλλο τερματικο γραφω :

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
Σε τερματικο και στην θεση (hercules@hercules:~/ros2_ws$ )
```
colcon build --install
source ~/.bashrc
ros2 run my_robot_controller pose_subscriber 
```
=> και σε αλλο terminal γραφω : (hercules@hercules:~$)
```
ros2 run turtlesim turtlesim_node
```
=> και σε αλλο terminal γραφω :
```
ros2 run my_robot_controller draw_circle
```
και βλεπω στο 1ο terminal (pose_subscriber) τα χ και τα y να αλλαζουν συνεχως 

## turtle_controller.py
Σε τερματικο και στην θεση (hercules@hercules:~/ros2_ws$ )
```
colcon build --symlink-install
source ~/.bashrc
ros2 run my_robot_controller turtle_controller
clear
cd
source .bashrc (αν κανω καποια αλλαγη στον κωδικα )
ros2 run my_robot_controller turtle_controller
```
=>και σε αλλο terminal 
```
ros2 run turtlesim turtlesim_node
```
=> και σε αλλο terminal γραφω :
```
ros2 run my_robot_controller pose_subscriber
```

<div style="text-align:center;">
    <img src="/4.png" alt="4" width="800">
</div>