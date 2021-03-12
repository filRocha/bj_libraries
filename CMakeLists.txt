cmake_minimum_required(VERSION 3.0.2)
project(bj_libraries)


# finding related packages
find_package(catkin REQUIRED COMPONENTS
  roscpp
)

# defining catkin imports and exports
catkin_package(
	INCLUDE_DIRS include 
	LIBRARIES quaternion dualquaternion
	CATKIN_DEPENDS roscpp
	)

# adding the include directory
include_directories(
	include
	${catkin_INCLUDE_DIRS})


# adding quaternion library
add_library(
	quaternion
	include/lib_quaternion/Quaternion.cpp
)
target_link_libraries(quaternion ${catkin_LIBRARIES})


# adding dual quaternion library
add_library(
	dualquaternion
	include/lib_dualquaternion/DualQuaternion.cpp
)
target_link_libraries(dualquaternion ${catkin_LIBRARIES})


# installing libraries
install(
  TARGETS quaternion dualquaternion
  ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  RUNTIME DESTINATION ${CATKIN_GLOBAL_BIN_DESTINATION}
)


install(
  DIRECTORY 
  include/lib_quaternion/ 
  include/lib_dualquaternion/
  DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION}
)