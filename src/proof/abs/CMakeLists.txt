cmake_minimum_required(VERSION 3.26)
set(COMPONENT_NAME abs)

include_directories(../../)
aux_source_directory(. SRCS)
list(REMOVE_ITEM SRCS "./abs.c")
list(REMOVE_ITEM SRCS "./absRefJ.c")
add_library(${COMPONENT_NAME} ${SRCS})
add_library(${PROJECT_NAME}::${SUBFOLDER_NAME}::${COMPONENT_NAME} ALIAS ${COMPONENT_NAME})
