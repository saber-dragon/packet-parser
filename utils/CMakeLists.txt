cmake_minimum_required(VERSION 3.0)

project(ip_packet)
set(CMAKE_CXX_STANDARD 11)

file (GLOB UTILS_HEADERs "*.hh")
file (GLOB UTILS_SRCs "*.cc")
file (GLOB UTILS_C_HEADERs "*.h")
file (GLOB UTILS_C_SRCs "*.c")

foreach(util_src ${UTILS_SRCs})
    get_filename_component(util_src_name ${util_src} NAME_WE)
    set(lib_name "${util_src_name}")
    add_library(${lib_name} ${UTILS_HEADERs} ${UTILS_C_HEADERs} ${util_src})
    target_link_libraries(${lib_name} ${saber_libs})
endforeach()

foreach(util_c_src ${UTILS_C_SRCs})
    get_filename_component(util_src_name ${util_c_src} NAME_WE)
    set(lib_name "${util_src_name}")
    add_library(${lib_name} ${UTILS_HEADERs} ${UTILS_C_HEADERs} ${util_c_src})
    target_link_libraries(${lib_name} ${saber_libs})
endforeach()