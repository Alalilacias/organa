add_library(organa-tasks
  src/Task.cpp
  # Add more task-related logic here
)

target_include_directories(organa-tasks PUBLIC
  ${CMAKE_CURRENT_SOURCE_DIR}/include
)

target_link_libraries(organa-tasks
  organa-core
)

add_executable(organa-tasks-cli
  src/main.cpp
)

target_link_libraries(organa-tasks-cli
  organa-tasks
)
