cmake_minimum_required(VERSION 2.8.3)
project(yolov3_deep_sort)

find_package(catkin REQUIRED COMPONENTS std_msgs sensor_msgs message_generation)

catkin_python_setup()

add_message_files(
  FILES
  BoundingBox_with_id.msg
  BoundingBoxes_with_id.msg
)


generate_messages(
  DEPENDENCIES std_msgs sensor_msgs
)



catkin_package(CATKIN_DEPENDS message_runtime)

#############
## Install ##
#############

install(PROGRAMS
  nodes/yolov3_deep_sort_node
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

install(DIRECTORY
  msg
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
