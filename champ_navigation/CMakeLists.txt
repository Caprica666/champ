cmake_minimum_required(VERSION 3.5)
project(champ_navigation)

find_package(ament_cmake REQUIRED)

install(
  DIRECTORY
  launch
  maps
  rviz
  DESTINATION share/${PROJECT_NAME}
)

ament_package()