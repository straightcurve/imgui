cmake_minimum_required(VERSION 3.16)
project(imgui)

set(CMAKE_CXX_STANDARD 17)

file(GLOB SOURCES *.h *.cpp backends/imgui_impl_glfw.cpp
     backends/imgui_impl_opengl3.cpp)

add_library(imgui STATIC ${SOURCES})
target_include_directories(imgui PUBLIC . backends)
target_link_libraries(imgui glfw GL)
