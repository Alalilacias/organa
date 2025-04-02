add_executable(organa
  src/launcher.cpp
)

target_include_directories(organa PUBLIC
  ${CMAKE_CURRENT_SOURCE_DIR}/include
)

target_link_libraries(organa
  organa-core
  organa-tasks
  organa-budget
  organa-tui
)
