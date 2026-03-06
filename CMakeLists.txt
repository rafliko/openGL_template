cmake_minimum_required(VERSION 3.10)
project(OpenGLApp)

# Include path
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)

# Executable sources
add_executable(${PROJECT_NAME} main.cpp glad.c)

# Link libraries
find_package(OpenGL REQUIRED)
if(WIN32)
    target_link_libraries(${PROJECT_NAME} PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/lib/glfw3.lib OpenGL::GL)
else()
    find_package(glfw3 REQUIRED)
    target_link_libraries(${PROJECT_NAME} PRIVATE glfw OpenGL::GL)
endif()