cmake_minimum_required(VERSION 3.8)
project(avyana_external_api_messages)

# find dependencies
find_package(ament_cmake_auto REQUIRED)
ament_auto_find_build_dependencies()
find_package(rosidl_default_generators REQUIRED)
rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/MapHash.msg"
  "msg/ResponseStatus.msg"
  "msg/TextFile.msg"
  "srv/GetTextFile.srv"
  DEPENDENCIES
    "builtin_interfaces"
    "diagnostic_msgs"
    "geometry_msgs"
  ADD_LINTER_TESTS
)

if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)
  ament_lint_auto_find_test_dependencies()
endif()

ament_auto_package()
