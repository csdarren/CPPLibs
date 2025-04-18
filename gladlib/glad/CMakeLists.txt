cmake_minimum_required(VERSION 3.10)

# Project name
project(gladlib)

# Specify the required C++ standard
set(CMAKE_CXX_STANDARD 11)

# Include directories
include_directories(${CMAKE_CURRENT_SOURCE_DIR})

# Create the static library
add_library(glad.c STATIC)

# Link any dependencies if needed
if (WIN32)
target_link_libraries(glad)
endif()

if (UNIX)
target_link_libraries(glad)
endif()