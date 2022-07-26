# sicktoolbox_wrapper
sicktoolbox_wrapper is a ROS wrapper for the outstanding sicktoolbox library for interfacing with the SICK LMS2XX lasers.

For this package to work on ROS-KINETIC, follow the instructions below:

1. change the working directory to catkin workspace
```
cd ~/catkin_ws/src
```

2. Clone the two required repositories
```
git clone <git url for sicktoolbox> (https://github.com/SantoshBanisetty/sicktoolbox.git)
git clone <git url for sicktoolbox_wrapper> (https://github.com/ros-drivers/sicktoolbox_wrapper.git)
```

3. Make the project
```
cd ~/catkin_ws
catkin_make
```

4. Make the required connections as shown in datasheet. 

5. Connect the USBtoRS232 and make sure the premissions are set properly.
```
ls -l /dev/ttyUSB0
``` 
You will see something similar to:
```
crw-rw-XX-
```
XX should be rw if not, so the following:
```
sudo chmod a+rw /dev/ttyUSB0
```

6. Now that the laser is configured properly, run a ros master like
```
roscore
```

7. Run the node as follows:(make sure you source the workspace)
```
rosrun sicktoolbox_wrapper sicklms _port:=/dev/ttyUSB0 _baud:=38400
```

8. You may use RVIZ to visualize or simply rostopic will suffice to confirm the working
```
rosrun rviz rviz
```

 
LaViRIA
-------


Hardware
--------

El robot en el que se instalo sicktoolbox_wrapper es un Pioneer 3-AT con un Escáner Laser 2D - LMS200 y una computadora de 64 bits. 


Software Instalado
------------------

El sistema operativo en el que se instalo el nodo rosaria fue Xubuntu 20.04 (Focal Fossa) con las herramientas que tiene instaladas por defecto, GNU C++ (g++/gcc), GNU Make con las herramientas de shell estándar y ROS Noetic Ninjemys. 


Instrucciones para instalar sicktoolbox_wrapper
-----------------------------------------------

1. En la carpeta src clonamos los repositorios desicktoolbox_wrapper y sicktoolbox

  git clone https://github.com/LaViRIA-code/sicktoolbox_wrapper.git
  git clone https://github.com/LaViRIA-code/sicktoolbox.git

2. Nos dirijimos a la espacio de trabajo (catkin_ws) y compilamos el código con el comando:

  catkin_make
