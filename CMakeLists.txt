cmake_minimum_required(VERSION 3.0)

project(egl-rtsp-server)

find_package(PkgConfig REQUIRED)
pkg_search_module(GLU REQUIRED IMPORTED_TARGET glu)

add_subdirectory(extern)

add_executable(server main.c egl.c egl.h)

target_link_libraries(server PkgConfig::GLU sigfn m cudartsp eglextloader)