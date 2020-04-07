cmake_minimum_required(VERSION 3.10)

#set the project name
project(ejercicio01 VERSION 1.0)

#add the executable
add_executable(ejercicio01 test.cpp)

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)

find_package(OpenGL REQUIRED)
find_package(glfw3 3.3 REQUIRED)
find_package(GLEW REQUIRED)
#find_package(PkgConfig REQUIRED)

#add_subdirectory(/usr/share/doc/libglfw3 BINARY_DIR)
#pkg_search_module(GLFW REQUIRED glfw3)

include_directories( ${OPENGL_INCLUDE_DIRS} ${GLFW_INCLUDE_DIRS} ${GLEW_INCLUDE_DIRS})

target_link_libraries(ejercicio01 ${OPENGL_LIBRARIES} ${GLFW_LIBRARIES} ${GLEW_LIBRARIES})

target_link_libraries(ejercicio01
    ${GLFW_STATIC_LIBRARIES}
    OpenGL::GL 
)

#target_compile_options(ejercicio01 PRIVATE -lGL -lGLU -lglut -lGLEW -lglfw3 -lX11 -lXxf86vm -lXrandr -lpthread -lXi -ldl -lXinerama -lXcursor)
