cmake_minimum_required(VERSION 3.0.2)
project(geometry_msgs_bridge)

## Compile as C++11, supported in ROS Kinetic and newer
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(catkin REQUIRED COMPONENTS
  message_generation
  message_runtime
  roscpp
  rospy
  std_msgs
#   geometry_msgs
)

# Message file
add_message_files(
  DIRECTORY
    msg
  FILES
    Twist.msg
    Vectort.msg

    # Accel.msg
)

generate_messages(
  DEPENDENCIES
    std_msgs
    # geometry_msgs
)

catkin_package(
  CATKIN_DEPENDS
    message_runtime
)