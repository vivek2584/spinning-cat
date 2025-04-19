cmake_minimum_required(VERSION 3.10)
project(SpinningCat)
set(CMAKE_CXX_STANDARD 17)

# Include directories
include_directories(
    ${CMAKE_SOURCE_DIR}/external
    ${CMAKE_SOURCE_DIR}/external/glad
    ${CMAKE_SOURCE_DIR}/external/glfw/include
)

# Link directories
link_directories(${CMAKE_SOURCE_DIR}/external/glfw/lib)

# Tell CMake to find OpenGL
find_package(OpenGL REQUIRED)

# Add glad as a static library
add_library(glad external/glad.c)

# Add your executable
add_executable(SpinningCat main.cpp)

# Link everything together
target_link_libraries(SpinningCat glad ${CMAKE_SOURCE_DIR}/external/glfw/lib/libglfw3.a ${OPENGL_gl_LIBRARY})

