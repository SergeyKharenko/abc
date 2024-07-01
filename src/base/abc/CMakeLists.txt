cmake_minimum_required(VERSION 3.26)
set(COMPONENT_NAME abc)

include_directories(../../)
aux_source_directory(. SRCS)
set_source_files_properties(${SRCS} PROPERTIES LANGUAGE CXX)
add_library(${COMPONENT_NAME} ${SRCS})
add_library(${PROJECT_NAME}::${SUBFOLDER_NAME}::${COMPONENT_NAME} ALIAS ${COMPONENT_NAME})
target_link_libraries(${COMPONENT_NAME}
        ${PROJECT_NAME}::proof::cec
        ${PROJECT_NAME}::base::abci
        ${PROJECT_NAME}::base::cmd
        ${PROJECT_NAME}::base::io
        ${PROJECT_NAME}::aig::hop
        ${PROJECT_NAME}::bool::dec
        ${PROJECT_NAME}::bool::kit
        ${PROJECT_NAME}::map::mio
        ${PROJECT_NAME}::misc::mem
        ${PROJECT_NAME}::misc::nm
        ${PROJECT_NAME}::opt::dar
        ${PROJECT_NAME}::proof::live
)
