cmake_minimum_required(VERSION 3.0)
project(packet_parser)

set(CMAKE_CXX_STANDARD 11)



include_directories(utils)
include_directories(ip)

add_subdirectory(utils)
add_subdirectory(ip)
# add_subdirectory(bgp)
