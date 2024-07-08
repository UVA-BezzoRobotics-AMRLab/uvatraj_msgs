cmake_minimum_required(VERSION 3.0.2)
project(uvatraj_msgs)

find_package(catkin REQUIRED COMPONENTS
  geometry_msgs
  std_msgs
  trajectory_msgs
  message_generation
)

add_message_files(
  DIRECTORY msg
  FILES
  ControlPoint.msg
)

add_service_files(
  DIRECTORY srv
  FILES
  RequestTraj.srv
  ExecuteTraj.srv
)

generate_messages(DEPENDENCIES geometry_msgs std_msgs trajectory_msgs)

catkin_package(CATKIN_DEPENDS message_runtime geometry_msgs std_msgs trajectory_msgs)
