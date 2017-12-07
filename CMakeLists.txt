cmake_minimum_required(VERSION 2.8.3)

include(cmake/HunterGate.cmake)
HunterGate(
    URL "https://github.com/ruslo/hunter/archive/v0.20.45.tar.gz"
    SHA1 "dbd69df4f1445cc8094325db2c0a51cb270c4f25"
)

project(roscpp_core)
hunter_add_package(Boost COMPONENTS date_time system thread)
hunter_add_package(catkin)
hunter_add_package(ros_console_bridge)

find_package(Boost REQUIRED COMPONENTS date_time system thread)

add_subdirectory(cpp_common)
add_subdirectory(roscpp_core)
add_subdirectory(roscpp_traits)
add_subdirectory(rostime)
add_subdirectory(roscpp_serialization)
