# Useful resources for getting started with CMake:
# https://github.com/ttroy50/cmake-examples/tree/master/02-sub-projects/A-basic
# https://cliutils.gitlab.io/modern-cmake/

# Require at least CMake version 3.15 or later for FetchContent
cmake_minimum_required(VERSION 3.15)

# Declare a project
project(VTIL-Hello)

# VTIL Requires C++20
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED true)

# Include the VTIL-Core project
include(FetchContent)

# See: https://cmake.org/cmake/help/v3.11/module/FetchContent.html
# This fetches the latest master for demonstratino purposes
FetchContent_Declare(
    VTIL-Core
    GIT_REPOSITORY https://github.com/vtil-project/VTIL-Core
    GIT_SHALLOW    true
)
FetchContent_MakeAvailable(VTIL-Core)

# Simple executable
add_executable(${PROJECT_NAME} VTIL-Hello.cpp)

# Link to VTIL
target_link_libraries(${PROJECT_NAME} PRIVATE VTIL)