cmake_minimum_required(VERSION 3.5)
project(elite_robots_simulation_gz)

find_package(ament_cmake REQUIRED)
find_package(rclpy REQUIRED)

install(DIRECTORY config launch
  DESTINATION share/${PROJECT_NAME}
  PATTERN "__pycache__" EXCLUDE
)

install(PROGRAMS
  scripts/gz_control.py
  DESTINATION lib/${PROJECT_NAME}
)
ament_package()
