cmake_minimum_required(VERSION 3.26)
set(COMPONENT_NAME abc)

include_directories(../../)
aux_source_directory(. SRCS)
add_library(${COMPONENT_NAME} ${SRCS})
add_library(${PROJECT_NAME}::${SUBFOLDER_NAME}::${COMPONENT_NAME} ALIAS ${COMPONENT_NAME})
target_link_libraries(${COMPONENT_NAME}
        ${PROJECT_NAME}::proof::cec
        ${PROJECT_NAME}::aig::hop
        ${PROJECT_NAME}::bool::dec
        ${PROJECT_NAME}::bool::kit
        ${PROJECT_NAME}::misc::mem
        ${PROJECT_NAME}::misc::nm
        ${PROJECT_NAME}::opt::dar
        ${PROJECT_NAME}::proof::live
)
