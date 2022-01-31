cmake_minimum_required(VERSION 3.5)
project(fkie_iop_msgs)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)
find_package(builtin_interfaces REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)

# Generate messages in the 'msg' folder
rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/Component.msg"
  "msg/DigitalResourceEndpoint.msg"
  "msg/DigitalResourceEndpoints.msg"
  "msg/HandoffRequest.msg"
  "msg/HandoffResponse.msg"
  "msg/Identification.msg"
  "msg/JausAddress.msg"
  "msg/Measurement.msg"
  "msg/MeasurementValue.msg"
  "msg/Node.msg"
  "msg/OcuCmd.msg"
  "msg/OcuCmdEntry.msg"
  "msg/OcuControlReport.msg"
  "msg/OcuFeedback.msg"
  "msg/OcuServiceInfo.msg"
  "msg/Service.msg"
  "msg/Subsystem.msg"
  "msg/System.msg"
  "msg/VisualSensorName.msg"
  "msg/VisualSensorNames.msg"
  "srv/QueryByAddr.srv"
  "srv/QueryIdentification.srv"
  DEPENDENCIES std_msgs
)

ament_export_dependencies(rosidl_default_runtime std_msgs)
ament_package()
