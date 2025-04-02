cmake_minimum_required(VERSION 3.16)
project(organa VERSION 0.1 LANGUAGES CXX)

# Set C++ version
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Set output directory
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

# Enable compile_commands.json for clangd
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

# Include directories
include_directories(include)

# Add subdirectories (each contains its own CMakeLists.txt)
add_subdirectory(core)
add_subdirectory(tasks)
add_subdirectory(budget)
add_subdirectory(tui)
add_subdirectory(launcher)
