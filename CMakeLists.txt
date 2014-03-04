cmake_minimum_required(VERSION 2.8.0)

#project name
project(SIGNALTAP)

list(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake/modules")
include(cmake/BuildType.cmake)

#where things go during compiling
set(SIGNALTAP_INSTALL_LIB_DIR lib)

set(EXECUTABLE_OUTPUT_PATH "${CMAKE_BINARY_DIR}/bin")
set(LIBRARY_OUTPUT_PATH "${CMAKE_BINARY_DIR}/lib")

#declare options -- test, measure and confirm
#option(BUILD_TESTING "Build SignalTap with testing enabled." ON)
option(BUILD_SHARED_LIBS "Build SignalTap with shared libraries." ON)

find_package(Eigen3 REQUIRED)

#where the action is at -- build the project
add_subdirectory(src)

# copy weights parameter files required for execution -- weights file is used to define weights for DistributedDiff class 
add_custom_command(
     OUTPUT ${CMAKE_CURRENT_BINARY_DIR}/weights.txt
     COMMAND ${CMAKE_COMMAND} -E copy ${CMAKE_CURRENT_SOURCE_DIR}/parameters/weights.txt ${CMAKE_CURRENT_BINARY_DIR}/weights.txt
     DEPENDS ${CMAKE_CURRENT_SOURCE_DIR}/parameters/weights.txt
   )



