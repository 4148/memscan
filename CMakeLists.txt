cmake_minimum_required(VERSION 3.2 FATAL_ERROR)
project(memscan VERSION 0.1.0 LANGUAGES CXX)

## build conditions:

if(NOT MSVC)
  message(FATAL_ERROR "Error: memscan only supports Windows right now!")
endif()

## build settings:

set(CMAKE_CXX_STANDARD 11)

if(NOT CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE Release CACHE STRING "Choose the build type" FORCE)
endif()

set(CMAKE_CXX_FLAGS_RELEASE -O2)

## files:

set(source_files
  Memscan.cpp
  main.cpp
  utils.cpp)

set(header_files
  Memscan.h
  utils.h)

## executable:

add_executable(${PROJECT_NAME}
  ${source_files}
  ${header_files})
