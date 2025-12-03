cmake_minimum_required(VERSION 3.5)
project(champ_bringup)

find_package(ament_cmake REQUIRED)

install(DIRECTORY launch
  DESTINATION shared/${PROJECT_NAME}
)

ament_package()