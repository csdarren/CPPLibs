cmake_minimum_required(VERSION 3.10)

# Project name
project(imguiLib)

# Specify the required C++ standard
set(CMAKE_CXX_STANDARD 11)

# Include directories
include_directories(include)

# Add the source files
set(SOURCES
    imgui_demo.cpp
    imgui_draw.cpp
    imgui_tables.cpp
    imgui_widgets.cpp
    imgui.cpp
    imgui_impl_opengl3.cpp
)

# Create the static library
add_library(imgui STATIC ${SOURCES})

# Link any dependencies if needed
if (WIN32)
target_link_libraries(imgui opengl32 glfw3 gdi32 winmm)
endif()

if (UNIX)
target_link_libraries(imgui opengl32 glfw3 gdi32)
endif()