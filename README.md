# ROS Wrapper and Node for open_karto
A ROS Package for Pose Graph SLAM that uses open_karto for the front end and SPA for backend.

## How to use on Ubuntu?
    1. This package has been tested well on Ubuntu 16.04 LTS, and the version of ROS is kinetic.
    
    2. Install Eigen3
        $ sudo apt-get install libeigen3-dev
        
    3. Install open_karto library
        $ cd catkin_ws/src/
        $ git clone https://github.com/ros-perception/open_karto
        $ cd..
        $ catkin_make
        
    4. clone and catkin_make
        $ cd catkin_ws/src/
        $ git clone https://github.com/WENJIAN0629/slam_karto
        $ cd..
        $ catkin_make
        
## Thanks

[1] https://github.com/ros-perception/open_karto

[2] https://github.com/ros-perception/slam_karto
