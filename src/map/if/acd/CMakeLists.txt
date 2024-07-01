cmake_minimum_required(VERSION 3.26)
set(COMPONENT_NAME acd)

include_directories(../../../)

add_library(${COMPONENT_NAME} ac_wrapper.cpp)
add_library(${PROJECT_NAME}::${SUBFOLDER_NAME}::${COMPONENT_NAME} ALIAS ${COMPONENT_NAME})