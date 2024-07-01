cmake_minimum_required(VERSION 3.26)
set(COMPONENT_NAME bbr)

include_directories(../../)
aux_source_directory(. SRCS)
list(REMOVE_ITEM SRCS "./bbr_.c")
set_source_files_properties(${SRCS} PROPERTIES LANGUAGE CXX)
add_library(${COMPONENT_NAME} ${SRCS})
add_library(${PROJECT_NAME}::${SUBFOLDER_NAME}::${COMPONENT_NAME} ALIAS ${COMPONENT_NAME})
