cmake_minimum_required(VERSION 3.16)
project(create_window)

find_package(glfw3 CONFIG REQUIRED)
find_package(glad CONFIG REQUIRED)

set(CMAKE_CXX_STANDARD 20)

find_package( OpenGL REQUIRED)

include_directories( ${OPENGL_INCLUDE_DIRS} )

set( GLFW_BUILD_EXAMPLES OFF CACHE BOOL  "GLFW lib only" )
set( GLFW_BUILD_TESTS OFF CACHE BOOL  "GLFW lib only" )
set( GLFW_BUILD_DOCS OFF CACHE BOOL  "GLFW lib only" )
set( GLFW_BUILD_INSTALL OFF CACHE BOOL  "GLFW lib only" )

add_executable(create_window main.cpp)

target_link_libraries(create_window PUBLIC ${OPENGL_LIBRARIES} ${GLFW_LIBRARIES} ${CMAKE_DL_LIBS} PRIVATE glfw glad::glad)