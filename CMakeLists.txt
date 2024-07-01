cmake_minimum_required(VERSION 3.26)

project(abc)
add_compile_options(-w)
add_compile_definitions(
        ABC_NAMESPACE=abc
        ABC_USE_PTHREADS
        ABC_USE_READLINE
        ABC_USE_CUDD=1
        ABC_USE_STDINT_H=1)

add_definitions(-fpermissive -g)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(src)
add_subdirectory(daemon)
