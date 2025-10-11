cmake_minimum_required(VERSION 4.1.2 FATAL_ERROR)

set(PROJECT_NAME battle_city)
project(${PROJECT_NAME})

set(CMAKE_CXX_STANDART 17)
add_executable(${PROJECT_NAME} 
    src/main.cpp
    src/Renderer/ShaderProgram.cpp
    src/Renderer/ShaderProgram.h)

add_subdirectory(external/glfw)

target_link_libraries(${PROJECT_NAME} glfw)

find_package(OpenGL REQUIRED)

target_link_libraries(${PROJECT_NAME} OpenGL::GL)

add_subdirectory(external/glad)
target_link_libraries(${PROJECT_NAME} glad)