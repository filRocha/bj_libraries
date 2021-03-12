cmake_minimum_required(VERSION 3.0.2)
project(bj_libraries)


find_package(catkin REQUIRED COMPONENTS
  roscpp
)


catkin_package(
	INCLUDE_DIRS include 
	LIBRARIES quaternion
	CATKIN_DEPENDS roscpp
	)


include_directories(
	include
	${catkin_INCLUDE_DIRS})

add_library(
	quaternion
	include/lib_quaternion/Quaternion.cpp
	)
target_link_libraries(quaternion ${catkin_LIBRARIES})


install(
  TARGETS quaternion
  ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  RUNTIME DESTINATION ${CATKIN_GLOBAL_BIN_DESTINATION}
)


install(
  DIRECTORY include/lib_quaternion/
  DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION}
)