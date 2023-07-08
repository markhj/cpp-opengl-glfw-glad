cmake_minimum_required(VERSION 3.25)
project(opengl_base)

set(CMAKE_CXX_STANDARD 14)

find_package(glfw3 REQUIRED)
find_package(OpenGL REQUIRED)
find_package(glm REQUIRED)
find_package(assimp CONFIG REQUIRED)

include_directories(libs/glad/include)
set(GLAD_SRC libs/glad/src/glad.c)

add_executable(opengl_base src/main.cpp ${GLAD_SRC})

target_link_libraries(opengl_base PRIVATE glfw opengl32 assimp glm)
