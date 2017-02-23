cmake_minimum_required(VERSION 2.6 FATAL_ERROR)
project(cork)

set (CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake_modules/)

# cflags for triangle.c
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -fPIC -O3 -DNO_TIMER -DREDUCED -DCDT_ONLY -DTRILIBRARY -DANSI_DECLARATORS")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fPIC -std=c++11 -O0 -g")
set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -O0 -g")

# gmp library
find_package(GMP REQUIRED)
include_directories(${GMP_INCLUDE_DIR])

add_subdirectory(src)

