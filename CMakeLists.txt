cmake_minimum_required(VERSION 3.26)

project(abc)
add_compile_options(-w)
add_compile_definitions(LIN64)
add_compile_definitions(ABC_NAMESPACE=abc)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(src)
add_subdirectory(daemon)
