# Require a recent version of cmake
cmake_minimum_required(VERSION 2.8.4 FATAL_ERROR)

# This project is C++ based.
project(HPXTutorials)

# This adds the HPX cmake configuration directory to the search path.
set(CMAKE_MODULE_PATH
    $ENV{HPX_DIR}/share/cmake-2.8/Modules)

# Instruct cmake to find the HPX settings
find_package(HPX)

include_directories(${HPX_INCLUDE_DIR})
link_directories(${HPX_LIBRARY_DIR})

set (sources 
	tutorial_1_Hello_World/main.cpp
	tutorial_1_Hello_World/info.txt
	)
# add example executable
add_hpx_executable(tutorial1
             SOURCES ${sources}
             ${HELLOWORLD_FLAGS} 
             FOLDER Basic
             COMPONENT_DEPENDENCIES)
