cmake_minimum_required(VERSION 2.8.3)
project(hb_core_msgs)

find_package(catkin REQUIRED COMPONENTS
  message_runtime
  geometry_msgs
  message_generation
  roscpp
  rospy
  std_msgs
)

add_message_files(
  FILES
    Velocity2D.msg
    Pose2D.msg
    Odom2D.msg
    Odom2DExtended.msg
    MotorCtrl.msg
    RobotStatus.msg
    ServoMotorCtrl.msg
  )

generate_messages()

catkin_package(
  CATKIN_DEPENDS CATKIN_DEPENDS message_runtime
)

install(DIRECTORY include/${PROJECT_NAME}/
  DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION}
  FILES_MATCHING PATTERN "*.h"
)
