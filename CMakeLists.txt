cmake_minimum_required(VERSION 3.5.0)
project(main VERSION 0.1.0 LANGUAGES C CXX)
cmake_policy(SET CMP0072 NEW)

# Find OpenGL package
find_package(OpenGL REQUIRED)

# Add executable target
add_executable(my_opengl_project 
    src/main.cpp 
    src/glad.c
)

# Include directories
target_include_directories(my_opengl_project PRIVATE include)

# Link libraries
target_link_libraries(my_opengl_project 
    glfw
    OpenGL::GL
)