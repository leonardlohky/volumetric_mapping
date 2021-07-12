cmake_minimum_required(VERSION 2.8.3)
project(volumetric_map_base)

set(OpenCV_DIR /usr/local/share/OpenCV)
find_package(OpenCV REQUIRED)
include_directories(include ${OpenCV_INCLUDE_DIRS})

find_package(catkin_simple REQUIRED)
catkin_simple(ALL_DEPS_REQUIRED)

add_definitions(-std=c++11)

#############
# LIBRARIES #
#############
cs_add_library(${PROJECT_NAME}
  src/world_base.cc
)

target_link_libraries(${PROJECT_NAME} ${OpenCV_LIBS})

##########
# EXPORT #
##########
cs_install()
cs_export()
