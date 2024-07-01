cmake_minimum_required(VERSION 3.26)
set(COMPONENT_NAME gia)

include_directories(../../)
aux_source_directory(. SRCS)
list(REMOVE_ITEM SRCS "./giaCTas2.c")
list(REMOVE_ITEM SRCS "./giaMffc.c")
list(REMOVE_ITEM SRCS "./giaProp.c")
list(REMOVE_ITEM SRCS "./giaSat.c")
set_source_files_properties(${SRCS} PROPERTIES LANGUAGE CXX)
add_library(${COMPONENT_NAME} ${SRCS})
add_library(${PROJECT_NAME}::${SUBFOLDER_NAME}::${COMPONENT_NAME} ALIAS ${COMPONENT_NAME})
target_link_libraries(${COMPONENT_NAME}
        ${PROJECT_NAME}::base::cmd
        ${PROJECT_NAME}::base::wlc
        ${PROJECT_NAME}::bool::bdc
        ${PROJECT_NAME}::map::mpm
        ${PROJECT_NAME}::misc::tim
        ${PROJECT_NAME}::opt::dar
        ${PROJECT_NAME}::proof::abs
        ${PROJECT_NAME}::proof::dch
        ${PROJECT_NAME}::proof::fra
        ${PROJECT_NAME}::sat::bmc)
