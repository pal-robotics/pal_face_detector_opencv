cmake_minimum_required(VERSION 2.8.3)
project(pal_face_detector_opencv)

find_package(catkin REQUIRED COMPONENTS
  cv_bridge
  image_transport    
  pal_detection_msgs
  sensor_msgs
  roscpp
)

catkin_package(
  INCLUDE_DIRS include
)

## Declare a cpp executable
add_executable(pal_face_detector_opencv src/face_detector.cpp)
target_link_libraries(pal_face_detector_opencv ${catkin_LIBRARIES})
add_dependencies(pal_face_detector_opencv pal_detection_msgs_generate_messages_cpp)

