add_library(organa-budget
  src/Budget.cpp
  # Add more budget-related logic here
)

target_include_directories(organa-budget PUBLIC
  ${CMAKE_CURRENT_SOURCE_DIR}/include
)

target_link_libraries(organa-budget
  organa-core
)

add_executable(organa-budget-cli
  src/main.cpp
)

target_link_libraries(organa-budget-cli
  organa-budget
)
