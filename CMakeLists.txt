cmake_minimum_required(VERSION 3.10)
project(SpinningCat)
set(CMAKE_CXX_STANDARD 17)

include_directories(
    ${CMAKE_SOURCE_DIR}/external
    ${CMAKE_SOURCE_DIR}/external/glad
    ${CMAKE_SOURCE_DIR}/external/glfw/include
)


link_directories(${CMAKE_SOURCE_DIR}/external/glfw/lib)

find_package(OpenGL REQUIRED)

add_library(glad external/glad.c)

add_executable(SpinningCat  main.cpp 
                            load/shaderClass.cpp
                            load/Texture.cpp
                            load/Camera.cpp
                            load/Model.cpp
                            load/Mesh.cpp
                            load/VAO.cpp
                            load/VBO.cpp
                            load/EBO.cpp)

# Link everything together
target_link_libraries(SpinningCat glad ${CMAKE_SOURCE_DIR}/external/glfw/lib/libglfw3.a ${OPENGL_gl_LIBRARY})

