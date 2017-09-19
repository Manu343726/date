project(date)
cmake_minimum_required(VERSION 3.4.2)

add_library(date tz.cpp)
target_include_directories(date PRIVATE "${CMAKE_SOURCE_DIR}")
target_include_directories(date PUBLIC "../${CMAKE_SOURCE_DIR}")

if(NOT MSVC)
    target_compile_options(date PRIVATE -std=c++11)
endif()
target_compile_definitions(date PUBLIC -DUSE_OS_TZDB=1)
