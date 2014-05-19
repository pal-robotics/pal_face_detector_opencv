cmake_minimum_required(VERSION 2.8.3)
project(pal_face_detector_opencv)

find_package(catkin REQUIRED COMPONENTS
  cv_bridge
  image_transport    
  pal_detection_msgs
  sensor_msgs
  roscpp
)

##########
# Flags ##
##########

add_definitions(-DPAL_MODULE_NAME=\"VISION\")
add_definitions(-DPAL_PROJECT_NAME=\"${PROJECT_NAME}\")
add_definitions(-DPAL_LIBRARY_NAME=\"${PROJECT_NAME}\")

###################################
## catkin specific configuration ##
###################################


catkin_package(
  CATKIN_DEPENDS sensor_msgs pal_detection_msgs
)

include_directories(${catkin_INCLUDE_DIRS})

###########
## Build ##
###########

## Declare a cpp executable
add_executable(pal_face_detector_opencv src/face_detector.cpp)
target_link_libraries(pal_face_detector_opencv ${catkin_LIBRARIES})
add_dependencies(pal_face_detector_opencv pal_detection_msgs_generate_messages_cpp)

