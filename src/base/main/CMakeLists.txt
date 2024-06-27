cmake_minimum_required(VERSION 3.26)

include_directories(../../)
aux_source_directory(. SRCS)
list(REMOVE_ITEM SRCS "./mainMC.c")
add_executable(abc_d ${SRCS})

#target_link_libraries(abc_d
#            abc::)