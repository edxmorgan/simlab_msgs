cmake_minimum_required(VERSION 3.10)
project(simlab_msgs)

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(geometry_msgs REQUIRED)

set(action_files
  "action/PlanVehicle.action"
)

rosidl_generate_interfaces(${PROJECT_NAME}
  ${action_files}
  DEPENDENCIES geometry_msgs
)

ament_export_dependencies(rosidl_default_runtime geometry_msgs)
ament_package()
