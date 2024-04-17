cmake_minimum_required(VERSION 3.16.3)

project(seriallib VERSION 0.0.1 LANGUAGES CXX)
set(CXX_CMAKE_STANDARD 20)
set(CXX_CMAKE_STANDARD_REQUIRED ON)

if (CMAKE_CXX_COMPILER_ID MATCHES "GNU")
    if(CMAKE_SYSTEM MATCHES "Linux")
        set(CMAKE_CXX_FLAGS  "${CMAKE_CXX_FLAGS} -std=c++20") # ALL WARNINGS
    endif()
    set(CMAKE_CXX_FLAGS  "${CMAKE_CXX_FLAGS} -Wall -O3") # ALL WARNINGS
elseif(CMAKE_CXX_COMPILER_ID MATCHES "MSVC")
    set(CMAKE_CXX_FLAGS  "${CMAKE_CXX_FLAGS} /MP")    # MULTICORE BUILDS
endif()


add_library(seriallib ./lib/serialib.cpp ./lib/serialib.h)