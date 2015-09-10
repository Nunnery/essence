cmake_minimum_required(VERSION 3.3)
project(essence)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${essence_SOURCE_DIR}/cmake/Modules)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(essence_VERSION_MAJOR 0)
set(essence_VERSION_MINOR 0)
set(essence_VERSION_PATCH 1)
set(essence_VERSION_STRING "${essence_VERSION_MAJOR}.${essence_VERSION_MINOR}.${essence_VERSION_PATCH}")

file(REMOVE ${PROJECT_SOURCE_DIR}/src/version.h)

configure_file(${PROJECT_SOURCE_DIR}/version.h.in ${PROJECT_SOURCE_DIR}/src/version.h @ONLY)

if(WIN32)
    set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -mwindows")
endif(WIN32)

add_subdirectory(src)