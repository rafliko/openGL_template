cmake_minimum_required(VERSION 3.10)
project(OpenGLApp)

# GLFW settings
find_package(glfw3 REQUIRED)

# Include paths
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)

# Source files
add_executable(${PROJECT_NAME} 
               ${CMAKE_CURRENT_SOURCE_DIR}/src/glad.c 
               ${CMAKE_CURRENT_SOURCE_DIR}/src/stb_image/stb_image.cpp 
               ${CMAKE_CURRENT_SOURCE_DIR}/src/shader/shader.cpp
               ${CMAKE_CURRENT_SOURCE_DIR}/src/main.cpp)

# Copy resources and shaders
# file(COPY "${CMAKE_CURRENT_SOURCE_DIR}/resources" DESTINATION "${CMAKE_CURRENT_BINARY_DIR}")
# file(COPY "${CMAKE_CURRENT_SOURCE_DIR}/shaders" DESTINATION "${CMAKE_CURRENT_BINARY_DIR}")

# Link libraries
target_link_libraries(${PROJECT_NAME} glfw)