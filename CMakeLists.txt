cmake_minimum_required(VERSION 3.10)
project(simlab_msgs)

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(std_msgs REQUIRED)

set(action_files
  "action/PlanVehicle.action"
)

set(msg_files
  "msg/ControllerPerformance.msg"
  "msg/ReferenceTargets.msg"
)

set(srv_files
  "srv/BackendRobotCommand.srv"
  "srv/BackendPoseCommand.srv"
  "srv/BackendWaypointCommand.srv"
)

rosidl_generate_interfaces(${PROJECT_NAME}
  ${action_files}
  ${msg_files}
  ${srv_files}
  DEPENDENCIES geometry_msgs std_msgs
)

ament_export_dependencies(rosidl_default_runtime geometry_msgs std_msgs)
ament_package()
