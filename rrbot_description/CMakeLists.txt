cmake_minimum_required(VERSION 3.10.2)
project(rrbot_description)
# Default to C11
if(NOT CMAKE_C_STANDARD)
  set(CMAKE_C_STANDARD 11)
endif()
# Default to C++14
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

if(NOT WIN32)
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)
find_package(control_msgs REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(rclcpp REQUIRED)
find_package(rclcpp_action REQUIRED)
find_package(std_msgs REQUIRED)

install(DIRECTORY urdf meshes config DESTINATION share/${PROJECT_NAME})

add_executable(position_control_test src/position_control_test.cpp)
ament_target_dependencies(position_control_test
  rclcpp
  rclcpp_action
  control_msgs
)

add_executable(effort_control_test src/effort_control_test.cpp)
ament_target_dependencies(effort_control_test
  rclcpp
  rclcpp_action
  control_msgs
)

## Install
install(
  TARGETS
    position_control_test
    effort_control_test
  DESTINATION
    lib/${PROJECT_NAME}
)

ament_package()


