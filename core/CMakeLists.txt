add_library(organa-core
  src/Config.cpp
  # Add more core sources here
)

target_include_directories(organa-core PUBLIC
  ${CMAKE_CURRENT_SOURCE_DIR}/include
)
