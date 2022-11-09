cmake_minimum_required(VERSION 3.8)
project(avyana_map_messages)

# find dependencies
find_package(ament_cmake_auto REQUIRED)
ament_auto_find_build_dependencies()

rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/HDMapBin.idl"
  "msg/HDMapSegment.idl"
  "msg/MapPrimitive.idl"
  "msg/HDMapRoute.idl"
  DEPENDENCIES
    "builtin_interfaces"
    "geometry_msgs"
    "nav_msgs"
    "std_msgs"
  ADD_LINTER_TESTS
)

if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)
  ament_lint_auto_find_test_dependencies()
endif()

ament_auto_package()
