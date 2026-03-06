cmake_minimum_required(VERSION 3.10)
project(OpenGLApp)

set(CMAKE_CXX_STANDARD 17)

# Find required packages
find_package(OpenGL REQUIRED)
find_package(glfw3 REQUIRED)

# Include path
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)

# Source files
add_executable(${PROJECT_NAME} src/main.cpp src/glad.c)

# Link libraries
target_link_libraries(${PROJECT_NAME} PRIVATE glfw OpenGL::GL)