cmake_minimum_required(VERSION 3.23)
project(opengl_base)

set(CMAKE_CXX_STANDARD 14)

find_package(glfw3 REQUIRED)
find_package(OpenGL REQUIRED)
find_package(glm REQUIRED)
find_package(Freetype REQUIRED)
find_package(assimp CONFIG REQUIRED)

include_directories(${FREETYPE_INCLUDE_DIRS})
include_directories(libs/glad/include)
include_directories(libs/stb)

set(GLAD_SRC libs/glad/src/glad.c libs/stb/stb_image.h)

add_executable(opengl_base src/main.cpp ${GLAD_SRC})

target_link_libraries(opengl_base PRIVATE glfw opengl32 assimp glm freetype)
