cmake_minimum_required(VERSION 2.8.3)
project(ole_lidar)

find_package(catkin REQUIRED COMPONENTS dynamic_reconfigure message_generation roscpp rospy rosgraph_msgs sensor_msgs)

#add_message_files(
#  FILES
#)

generate_messages(
  DEPENDENCIES
  sensor_msgs
)

generate_dynamic_reconfigure_options(
    cfg/Lidar.cfg
)

catkin_package(
  CATKIN_DEPENDS dynamic_reconfigure message_runtime roscpp rospy rosgraph_msgs sensor_msgs
)

install(PROGRAMS scripts/scan DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})

install(DIRECTORY launch
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
