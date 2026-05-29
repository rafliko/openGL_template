cmake_minimum_required(VERSION 3.10)
project(openGL_template VERSION 1.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

file(COPY shaders DESTINATION ${CMAKE_CURRENT_BINARY_DIR})

find_package(GLEW REQUIRED)
find_package(glfw3 REQUIRED)

aux_source_directory(src SRC_FILES)
add_executable(${PROJECT_NAME} ${SRC_FILES})

target_link_libraries(${PROJECT_NAME} PRIVATE GLEW::GLEW glfw)