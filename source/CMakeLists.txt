cmake_minimum_required(VERSION 3.0)
project(eXosip)
SET(EXOSIP_SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR})
SET(THIRD_PARTY_LIB_TARGET_DIRECTORY ${EXOSIP_SOURCE_DIR}/libs/)
add_subdirectory(./tools/)
add_subdirectory(./src/)
add_subdirectory(./third_party/)