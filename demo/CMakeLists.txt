cmake_minimum_required(VERSION 3.26)

set_source_files_properties(demo.c PROPERTIES LANGUAGE CXX)
set_source_files_properties(starter.c PROPERTIES LANGUAGE CXX)

add_executable(demo demo.c)
add_executable(starter starter.c)

add_dependencies(demo abc_daemon_lib)
target_link_libraries(demo
        PUBLIC
        abc_daemon_lib)