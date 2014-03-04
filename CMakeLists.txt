cmake_minimum_required(VERSION 2.8.0)

#project name
project(SIGNALTAP)

list(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake/modules")

#where things go during compiling
set(SIGNALTAP_INSTALL_LIB_DIR lib)

set(EXECUTABLE_OUTPUT_PATH "${CMAKE_BINARY_DIR}/bin")
set(LIBRARY_OUTPUT_PATH "${CMAKE_BINARY_DIR}/lib")

#declare options -- test, measure and confirm
#option(BUILD_TESTING "Build SignalTap with testing enabled." ON)

#add external dependencies
include(${PROJECT_SOURCE_DIR}/cmake/FindEigen3.cmake)

#and finally where the action is at -- build the project
add_subdirectory(src)


