For kinetic:

sudo apt-get install ros-kinetic-navigation
sudo apt-get install ros-kinetic-map-server
sudo apt-get install ros-kinetic-move-base
sudo apt-get install ros-kinetic-amcl

For noetic:

sudo apt-get install ros-noetic-navigation
sudo apt-get install ros-noetic-map-server
sudo apt-get install ros-noetic-move-base
sudo apt-get install ros-noetic-amcl


PGM Map Creator: Install Dependencies
sudo apt-get install libignition-math2-dev protobuf-compiler


apt-cache search libignition-math

For gazebo 11:
sudo apt-get install libignition-math4-dev   



If you are using ROS Noetic, the pgm_map_creator package may not be fully compatible as it was primarily developed for earlier versions of ROS.

However, there are alternative methods to create a PGM map in ROS Noetic. One option is to use the map_server package, which is a standard ROS package for handling map-related operations.

To create a PGM map using the map_server package, you can follow these steps:

    Install the map_server package:

    sudo apt-get install ros-noetic-map-server

    Generate a map using Gazebo or any other method you prefer. Make sure to save the map as an image file (e.g., PNG).

    Convert the image file to a PGM file using the convert command from the ImageMagick package:

    convert map_image.png map.pgm

    Create a YAML file that describes the map. The YAML file should include the resolution, origin, and image file path. Here is an example:

    image: /path/to/map.pgm
    resolution: 0.05
    origin: [-10.0, -10.0, 0.0]

    Launch the map_server node with the YAML file:

    rosrun map_server map_server map.yaml

    This will start the map_server node and load the map.

By following these steps, you should be able to create and load a PGM map in ROS Noetic using the map_server package.


https://knowledge.udacity.com/questions/877949
However, it is very likely to come across further issues down the line as pgm_map_creator is not really compatible with ROS Noetic. you can create the map in the Udacity workspace and, once generated, continue working on your VM).



rqt_graph
$ rosrun rqt_graph rqt_graph

No transform from [map] to [odom]
https://knowledge.udacity.com/questions/62205
https://knowledge.udacity.com/questions/653924

catkin_make
source devel/setup.bash

roslaunch my_robot world.launch

roslaunch ball_chaser ball_chaser.launch



