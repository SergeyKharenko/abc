cmake_minimum_required(VERSION 3.26)
set(COMPONENT_NAME io)

include_directories(../../)
aux_source_directory(. SRCS)
add_library(${COMPONENT_NAME} ${SRCS})
add_library(${PROJECT_NAME}::${SUBFOLDER_NAME}::${COMPONENT_NAME} ALIAS ${COMPONENT_NAME})
target_link_libraries(${COMPONENT_NAME}
        ${PROJECT_NAME}::base::ver
        ${PROJECT_NAME}::misc::bzlib
        ${PROJECT_NAME}::misc::bbl
        ${PROJECT_NAME}::misc::parse)