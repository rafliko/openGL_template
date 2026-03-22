cmake_minimum_required(VERSION 3.10)
project(OpenGLApp)

# glfw settings
set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/libs/glfw-3.4)

# Include paths
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/libs/glad/include)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/libs/glfw-3.4/include)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/libs/glm)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/libs/stb_image)

# Source files
add_executable(${PROJECT_NAME} 
               ${CMAKE_CURRENT_SOURCE_DIR}/libs/glad/src/glad.c
               ${CMAKE_CURRENT_SOURCE_DIR}/libs/stb_image/stb_image.cpp
               ${CMAKE_CURRENT_SOURCE_DIR}/src/shader/shader.cpp
               ${CMAKE_CURRENT_SOURCE_DIR}/src/main.cpp)

# Copy resources and shaders
file(COPY "${CMAKE_CURRENT_SOURCE_DIR}/shaders" DESTINATION "${CMAKE_CURRENT_BINARY_DIR}")

# Link glfw
target_link_libraries(${PROJECT_NAME} glfw)