# CMakeList.txt : CMake project for TriangleGL, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)

project(Ejem2)

SET (exec "TriangleGL.cpp" "glad.c")

link_directories(${CMAKE_SOURCE_DIRECTORY} "lib")

include_directories("include")

# Add source to this project's executable.
add_executable (Ejem2 ${exec})

# TODO: Add tests and install targets if needed.
target_link_libraries(Ejem2 PUBLIC glfw3)
target_link_libraries(Ejem2 PUBLIC opengl32)