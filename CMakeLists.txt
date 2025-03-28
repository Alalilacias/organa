cmake_minimum_required(VERSION 3.16)
project(organa VERSION 0.1 LANGUAGES CXX)

# Set C++ version
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Set output directory
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

# Include directories
include_directories(include)

# Find all source files
file(GLOB_RECURSE SOURCES CONFIGURE_DEPENDS
    src/*.cpp
)

# Build the executable
add_executable(organa ${SOURCES})

# Link libraries here if needed (e.g. yaml-cpp, nlohmann/json later)
# target_link_libraries(organa PRIVATE ...)
