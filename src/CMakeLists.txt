set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wno-deprecated-declarations -Wreturn-type -Wuninitialized -Wunused-variable -std=c++0x")

#set(REQUIRED_LIBS boost_system)
find_package(Boost 1.46 COMPONENTS filesystem unit_test_framework REQUIRED)
message(status "** Boost Include: ${Boost_INCLUDE_DIR}")
message(status "** Boost Libraries: ${Boost_LIBRARY_DIRS}")
message(status "** Boost Libraries: ${Boost_LIBRARIES}")

include_directories(${EIGEN3_INCLUDE_DIR})
include_directories("${CMAKE_CURRENT_SOURCE_DIR}/include")

################  THIS IS THE SIGNALTAP LIBRARY
add_library(signal-tap
  SignalTap.cpp)

#target_link_libraries (signal-tap ${REQUIRED_LIBS})# is this right?
#set_target_properties(signal-tap PROPERTIES SOVERSION 1)


# add the install targets
#install (TARGETS signal-tap DESTINATION bin)
#install (FILES "${PROJECT_BINARY_DIR}/SignalTap.hpp"        
#         DESTINATION include)

############## Define test executables
#add_executable(signaltap_test signaltap-test.cpp)




