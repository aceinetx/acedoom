cmake_minimum_required(VERSION 3.20)
project(acedoom)
file(GLOB SOURCES doomgeneric/*.c doomgeneric/*.cpp)
file(GLOB IMGUI_SOURCES imgui/src/*.cpp)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED YES)

add_executable("acedoom" WIN32 ${SOURCES} ${IMGUI_SOURCES})
target_include_directories("acedoom" PUBLIC "include/SDL2" "include/" "imgui/include" "imgui/")
target_link_directories("acedoom" PUBLIC "lib/")
target_link_libraries("acedoom" ${CMAKE_CURRENT_SOURCE_DIR}/lib/SDL2.lib ${CMAKE_CURRENT_SOURCE_DIR}/lib/SDL2main.lib)