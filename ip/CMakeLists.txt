cmake_minimum_required(VERSION 3.0)

project(ip_packet)
set(CMAKE_CXX_STANDARD 11)

file (GLOB IP_HEADERs "*.hh")
file (GLOB IP_SRCs "*.cc")
file (GLOB IP_C_HEADERs "*.h")
file (GLOB IP_C_SRCs "*.c")

foreach(ip_src ${IP_SRCs})
    get_filename_component(ip_src_name ${ip_src} NAME_WE)
    set(lib_name "${ip_src_name}")
    add_library(${lib_name} ${IP_HEADERs} ${IP_C_HEADERs} ${ip_src})
    target_link_libraries(${lib_name} ${saber_libs})
endforeach()

foreach(ip_c_src ${IP_C_SRCs})
    get_filename_component(ip_src_name ${ip_c_src} NAME_WE)
    set(lib_name "${ip_src_name}")
    add_library(${lib_name} ${IP_HEADERs} ${IP_C_HEADERs} ${ip_c_src})
    target_link_libraries(${lib_name} ${saber_libs})
endforeach()