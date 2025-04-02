add_library(organa-tui
  src/TUI.cpp
  # Add more TUI logic here
)

target_include_directories(organa-tui PUBLIC
  ${CMAKE_CURRENT_SOURCE_DIR}/include
)

target_link_libraries(organa-tui
  organa-core
)

add_executable(organa-tui-cli
  src/main.cpp
)

target_link_libraries(organa-tui
  organa-core
)
