# Minimum CMake version
cmake_minimum_required(VERSION 3.10)

# Project name
project(MyProject)

# Set C++ standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Add executable target
file(GLOB SRC_FILES 
    "src/*.cpp"
)
add_executable(main ${SRC_FILES})

# Add include directories
target_include_directories(main PRIVATE ../inc)


