cmake_minimum_required(VERSION 3.10)
project(OpenGLApp)

set(CMAKE_CXX_STANDARD 17)

# 1. Dodajemy ścieżki do nagłówków (nasz lokalny folder include)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)

# 2. Tworzymy plik wykonywalny
add_executable(OpenGLApp main.cpp glad.c)

# 3. Linkowanie bibliotek
if(WIN32)
    # Na Windowsie wskazujemy konkretny plik .lib
    target_link_libraries(OpenGLApp PRIVATE 
        ${CMAKE_CURRENT_SOURCE_DIR}/lib/glfw3.lib
        opengl32.lib
    )
else()
    # Na Linuxie nadal używamy systemowych, bo tam są zawsze dostępne
    find_package(glfw3 REQUIRED)
    find_package(OpenGL REQUIRED)
    target_link_libraries(OpenGLApp PRIVATE glfw OpenGL::GL)
endif()