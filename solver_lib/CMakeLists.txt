cmake_minimum_required(VERSION 3.4)
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
project(solver_lib)

add_library(solver STATIC ${CMAKE_CURRENT_SOURCE_DIR}/solver.cpp)
include_directories(${CMAKE_CURRENT_SOURCE_DIR})