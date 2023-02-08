cmake_minimum_required(VERSION 2.8.3)
project(hector_uav_msgs)

find_package(catkin REQUIRED message_generation std_msgs geometry_msgs actionlib_msgs)

add_message_files(
  FILES
  Altimeter.msg
)

# add_service_files(
#  FILES
#  EnableMotors.srv
# )

# add_action_files(
#   DIRECTORY
#     action
#   FILES
#     Pose.action
#     Landing.action
#     Takeoff.action
# )

generate_messages(
  DEPENDENCIES
  # actionlib_msgs
  std_msgs
  geometry_msgs
)

catkin_package(
  INCLUDE_DIRS include
  CATKIN_DEPENDS message_runtime std_msgs
)

install(DIRECTORY include/${PROJECT_NAME}/
  DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION}
)

