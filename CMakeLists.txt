cmake_minimum_required(VERSION 3.10)
project(OpenGLApp)

set(CMAKE_CXX_STANDARD 17)

# GLFW settings
set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)

add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/external/glfw)

# Include paths
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/external/glad/include)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/external/stb_image)

# Source files
add_executable(${PROJECT_NAME} 
               ${CMAKE_CURRENT_SOURCE_DIR}/external/glad/src/glad.c 
               ${CMAKE_CURRENT_SOURCE_DIR}/external/stb_image/stb_image.cpp 
               ${CMAKE_CURRENT_SOURCE_DIR}/src/shader/shader.cpp
               ${CMAKE_CURRENT_SOURCE_DIR}/src/main.cpp)

# Copy resources and shaders
file(COPY "${CMAKE_CURRENT_SOURCE_DIR}/resources" DESTINATION "${CMAKE_CURRENT_BINARY_DIR}")
file(COPY "${CMAKE_CURRENT_SOURCE_DIR}/shaders" DESTINATION "${CMAKE_CURRENT_BINARY_DIR}")

# Link libraries
target_link_libraries(${PROJECT_NAME} glfw)