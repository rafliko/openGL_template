cmake_minimum_required(VERSION 3.10)
project(OpenGLApp)

include(FetchContent)

# glfw
FetchContent_Declare(
    glfw
    GIT_REPOSITORY https://github.com/glfw/glfw.git
    GIT_TAG 3.4
)
set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)

# glm
FetchContent_Declare(
    glm
    GIT_REPOSITORY https://github.com/g-truc/glm.git
    GIT_TAG 1.0.3
)
    
# glad
FetchContent_Declare(
    glad
    GIT_REPOSITORY https://github.com/Dav1dde/glad.git
    GIT_TAG v0.1.36
)
set(CMAKE_POLICY_VERSION_MINIMUM 3.5)

FetchContent_MakeAvailable(glfw glm glad)

# Source files
add_executable(
    ${PROJECT_NAME}
    ${CMAKE_CURRENT_SOURCE_DIR}/src/shader/shader.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/src/main.cpp
)

# Copy shaders to build directory
file(COPY "${CMAKE_CURRENT_SOURCE_DIR}/shaders" DESTINATION "${CMAKE_CURRENT_BINARY_DIR}")

# Link glfw and glad
target_link_libraries(${PROJECT_NAME} PRIVATE glfw glad)

# Add glm headers
target_include_directories(${PROJECT_NAME} PRIVATE ${glm_SOURCE_DIR})