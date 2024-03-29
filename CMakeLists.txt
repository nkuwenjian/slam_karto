cmake_minimum_required(VERSION 2.8.3)
project(slam_karto)

# Add new CMake Modules
LIST(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake_modules)

find_package(catkin REQUIRED COMPONENTS
  message_filters
  cmake_modules
  nav_msgs
  roscpp
  rosconsole
  sensor_msgs
  tf
  visualization_msgs
  open_karto
)

find_package(Eigen3 REQUIRED)
find_package(CSparse REQUIRED)

catkin_package()

include_directories(include
  third_party
  ${catkin_INCLUDE_DIRS}
  ${EIGEN3_INCLUDE_DIRS}
  ${CSPARSE_INCLUDE_DIR}
)

add_library(spa_solver src/spa_solver.cpp third_party/spa/csparse.cpp third_party/spa/spa2d.cpp)
target_link_libraries(spa_solver
  ${catkin_LIBRARIES}
  ${CSPARSE_LIBRARY}
)

add_executable(slam_karto src/slam_karto.cpp)
target_link_libraries(slam_karto spa_solver)
