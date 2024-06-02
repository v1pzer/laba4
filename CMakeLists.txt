cmake_minimum_required(VERSION 3.4)
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
project(subtask)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/formatter_ex_lib)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/formatter_lib)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/solver_lib)

add_library(formatter_lib STATIC ${CMAKE_CURRENT_SOURCE_DIR}/formatter_lib/formatter.cpp)
add_library(formatter_ex_lib STATIC ${CMAKE_CURRENT_SOURCE_DIR}/formatter_ex_lib/formatter_ex.cpp)
add_library(solver_lib STATIC ${CMAKE_CURRENT_SOURCE_DIR}/solver_lib/solver.cpp)
target_link_libraries(formatter_ex_lib formatter_lib)

add_executable(hello_world ${CMAKE_CURRENT_SOURCE_DIR}/hello_world_application/hello_world.cpp)
target_link_libraries(hello_world formatter_ex_lib)

add_executable(solver_app ${CMAKE_CURRENT_SOURCE_DIR}/solver_application/equation.cpp)
target_link_libraries(solver_app formatter_ex_lib)
target_link_libraries(solver_app solver_lib)

