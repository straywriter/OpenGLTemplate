cmake_minimum_required(VERSION 3.0)

project(OpenGLTemplate)

# External Library add_subdirectory(External)
add_subdirectory(External/glad)
add_subdirectory(External/glfw)


set(dir ./External/glad)
add_subdirectory(./Doc)

find_package(OpenGL REQUIRED)


add_executable(Example Example/Example1.cpp)
target_link_libraries(Example glfw glad  opengl32 )
