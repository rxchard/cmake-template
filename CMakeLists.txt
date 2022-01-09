cmake_minimum_required(VERSION 3.14.0)

project(template)

message(STATUS "Configuring CMake...")
#  Place for additional CMake configuration and build deps like CPM
add_subdirectory(cmake)

message(STATUS "Build Type: ${CMAKE_BUILD_TYPE}")

file(GLOB_RECURSE PROJECT_SOURCE_FILES ${CMAKE_CURRENT_SOURCE_DIR}/src/**.c)
add_executable(${PROJECT_NAME} ${PROJECT_SOURCE_FILES})

message(STATUS "Configuring Dependencies...")
# Configure other deps that should be included
add_subdirectory(pm)
