cmake_minimum_required(VERSION 3.0)

project(bgp_packet)


file (GLOB BP_HEADERs "*.hh")
file (GLOB BP_SRCs "*.cc")

foreach(bp_src ${BP_SRCs})
    get_filename_component(bp_src_name ${bp_src} NAME_WE)
    set(lib_name "${bp_src_name}")
    add_library(${lib_name} ${BP_HEADERs} ${bp_src})
    target_link_libraries(${lib_name} ${saber_libs})
endforeach()