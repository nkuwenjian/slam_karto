# ROS Wrapper for Karto SLAM with SPA solver
A ROS package for 2D laser SLAM that uses open-karto package for the front end and SPA solver for backend.

## How to use on Ubuntu?
    1. This package has been tested well in Ubuntu 16.04 with ROS Kinetic.
    
    2. Install Eigen3 and CXSparse 
        $ sudo apt-get install libeigen3-dev libsuitesparse-dev

    3. Clone and build open-karto package
        $ cd ~/catkin_ws/src/
        $ git clone https://github.com/ros-perception/open_karto.git
        $ cd ..
        $ catkin_make

    4. Clone and build this package
        $ cd ~/catkin_ws/src/
        $ git clone https://github.com/nkuwenjian/slam_karto.git
        $ cd ..
        $ catkin_make

    5. Run offline rosbag
        $ source ~/catkin_ws/devel/setup.bash
        $ roslaunch slam_karto karto_slam.launch
        $ rosbag play <rosbagfile> --clock

## Topics

### Subscribed topics
- `/scan` ([sensor_msgs/LaserScan](http://docs.ros.org/melodic/api/sensor_msgs/html/msg/LaserScan.html))
- `/tf` ([tf2_msgs/TFMessage](http://docs.ros.org/melodic/api/tf2_msgs/html/msg/TFMessage.html))

### Published topics
- `/map` ([nav_msgs/OccupancyGrid](http://docs.ros.org/melodic/api/nav_msgs/html/msg/OccupancyGrid.html))
- `/map_metadata` ([nav_msgs/MapMetaData](http://docs.ros.org/melodic/api/nav_msgs/html/msg/MapMetaData.html))
- `/tf` ([tf2_msgs/TFMessage](http://docs.ros.org/melodic/api/tf2_msgs/html/msg/TFMessage.html))
- `/visualization_marker_array` ([visualization_msgs/MarkerArray](http://docs.ros.org/melodic/api/visualization_msgs/html/msg/MarkerArray.html))
        
## Thanks

[1] https://github.com/ros-perception/slam_karto
