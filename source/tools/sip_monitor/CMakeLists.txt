cmake_minimum_required(VERSION 3.0)
project(sip_monitor)

add_compile_options(-DWIN32)
include_directories(${EXOSIP_SOURCE_DIR}/third_party/libosip2-5.3.1/include/)
include_directories(${EXOSIP_SOURCE_DIR}/third_party/getopt_for_windows/)
include_directories(${EXOSIP_SOURCE_DIR}/include/)

link_directories(${THIRD_PARTY_LIB_TARGET_DIRECTORY})
add_executable(sip_monitor ./sip_monitor.c ${EXOSIP_SOURCE_DIR}/third_party/getopt_for_windows/getopt.c)
target_link_libraries(sip_monitor exosip.lib)
target_link_libraries(sip_monitor libosip2.lib)
target_link_libraries(sip_monitor Ws2_32.lib)

#add_executable(sip_storm ./sip_storm.c)
#target_link_libraries(sip_storm exosip.lib)
#target_link_libraries(sip_storm libosip2.lib)
#target_link_libraries(sip_storm Ws2_32.lib)
#add_executable(sip_monitor ./sip_monitor.c)