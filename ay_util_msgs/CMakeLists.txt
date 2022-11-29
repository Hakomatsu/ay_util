cmake_minimum_required(VERSION 2.4.6)
project(ay_util_msgs)

find_package(catkin REQUIRED COMPONENTS
  message_generation
  std_msgs
  moveit_msgs
  )

add_message_files(
  FILES
  Float64Stamped.msg
  Int32Stamped.msg
  StringStamped.msg
  )

add_service_files(
  FILES
  DxlGMove.srv
  DxlIO.srv
  GetAllowedCollisionMatrix.srv
  GetStateValidity.srv
  GetTrajectoryValidity.srv
  SetPlanningSceneDiff.srv
  )

generate_messages(
  DEPENDENCIES std_msgs moveit_msgs
)

catkin_package(
  CATKIN_DEPENDS message_runtime
  )

include_directories(
  ${catkin_INCLUDE_DIRS}
  )
