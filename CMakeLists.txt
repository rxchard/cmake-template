cmake_minimum_required(VERSION 3.16.0)

# Project name
project(template 
    LANGUAGES C CXX)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

message(STATUS "Configuring CMake...")
add_subdirectory(cmake)

message(STATUS "Build Type: ${CMAKE_BUILD_TYPE}")

file(GLOB_RECURSE PROJECT_SOURCE_FILES ${CMAKE_CURRENT_SOURCE_DIR}/src/**.c)
add_executable(${PROJECT_NAME} ${PROJECT_SOURCE_FILES})

message(STATUS "Configuring Dependencies...")
add_subdirectory(dependencies)
