cmake_minimum_required(VERSION 2.4.6)
project(ay_util)

# Some packages such as MoveIt! needs to be compiled with C++11
add_compile_options(-std=c++11)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  eigen_conversions
  moveit_core
  moveit_ros_planning_interface
  ay_util_msgs
  )

catkin_package(
  )

include_directories(
  ${catkin_INCLUDE_DIRS}
  )

add_executable(state_validity_checker_node
  src/state_validity_checker_node.cpp
  )
target_link_libraries(state_validity_checker_node
  ${catkin_LIBRARIES}
  )
