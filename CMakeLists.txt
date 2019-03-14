cmake_minimum_required(VERSION 2.8.3)
project(mobro)

find_package(catkin REQUIRED COMPONENTS
  nav_msgs
  sensor_msgs
  dynamic_reconfigure
)

generate_dynamic_reconfigure_options(
  control/Gains.cfg
)



catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES mobro
#  CATKIN_DEPENDS nav_msgs sensor_msgs
#  DEPENDS system_lib
)

## Specify additional locations of header files
## Your package locations should be listed before other locations
include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)

