cmake_minimum_required(VERSION 3.10)
project(OpenGLApp)

set(CMAKE_CXX_STANDARD 17)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)

add_executable(OpenGLApp main.cpp glad.c)

# Link libraries
if(WIN32)
    target_link_libraries(OpenGLApp PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/lib/glfw3.lib opengl32.lib)
else()
    find_package(glfw3 REQUIRED)
    find_package(OpenGL REQUIRED)
    target_link_libraries(OpenGLApp PRIVATE glfw OpenGL::GL)
endif()