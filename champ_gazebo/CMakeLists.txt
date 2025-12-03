
cmake_minimum_required(VERSION 3.5)
project(champ_gazebo)

add_compile_options(-std=c++17)
if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)
find_package(rclpy REQUIRED)
find_package(champ_msgs REQUIRED) 
find_package(champ REQUIRED) 

install(
  DIRECTORY
  launch
  config
  DESTINATION share/${PROJECT_NAME}
)

install(PROGRAMS
  scripts/imu_sensor.py
  scripts/odometry_tf.py
  scripts/odometry.py
  DESTINATION lib/${PROJECT_NAME}
)

#add_library(contact_sensor SHARED src/contact_sensor.cpp)
#ament_target_dependencies(contact_sensor ${dependencies})
#target_link_libraries(contact_sensor)

#install(TARGETS contact_sensorDESTINATION lib/${PROJECT_NAME})

set(dependencies
  rclcpp
  rclpy
  champ
  champ_msgs
  urdf
)

ament_export_dependencies(${dependencies})
ament_package()