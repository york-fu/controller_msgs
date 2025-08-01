cmake_minimum_required(VERSION 3.10)
project(controller_msgs)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(std_msgs REQUIRED)
find_package(sensor_msgs REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(rosidl_default_generators REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/JointState.msg"
  "msg/JointCmd.msg"
  "msg/Spatial.msg"
  "msg/SpatialArray.msg"
  "msg/SpatialStamped.msg"
  "msg/SpatialArrayStamped.msg"

  "srv/Empty.srv"
  "srv/Trigger.srv"
  "srv/SetBool.srv"
  "srv/SetInt8.srv"
  "srv/SetInt16.srv"
  "srv/SetInt32.srv"
  "srv/SetUInt8.srv"
  "srv/SetUInt16.srv"
  "srv/SetUInt32.srv"
  "srv/SetFloat32.srv"
  "srv/SetFloat64.srv"
  "srv/GetBool.srv" 
  "srv/GetInt8.srv"
  "srv/GetInt16.srv"
  "srv/GetInt32.srv"
  "srv/GetUInt8.srv"
  "srv/GetUInt16.srv"
  "srv/GetUInt32.srv"
  "srv/GetFloat32.srv"
  "srv/GetFloat64.srv"

  DEPENDENCIES std_msgs sensor_msgs geometry_msgs
)

if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)
  # the following line skips the linter which checks for copyrights
  # comment the line when a copyright and license is added to all source files
  set(ament_cmake_copyright_FOUND TRUE)
  # the following line skips cpplint (only works in a git repo)
  # comment the line when this package is in a git repo and when
  # a copyright and license is added to all source files
  set(ament_cmake_cpplint_FOUND TRUE)
  ament_lint_auto_find_test_dependencies()
endif()

ament_package()
