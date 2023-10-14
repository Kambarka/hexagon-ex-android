# = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = =

# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# CMAKE
# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

set(SOLUTION_CMAKE_VERSION 3.22)
cmake_minimum_required(VERSION ${SOLUTION_CMAKE_VERSION})

# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# PROJECT
# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

set(HEXAGON_EX_VERSION 0.1.0)
project("HexagonEX.Android" VERSION ${HEXAGON_EX_VERSION})

# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# GLOBALS
# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

set(SOLUTION_DIR ${CMAKE_SOURCE_DIR})
set(SOLUTION_SOURCES_DIR "${SOLUTION_DIR}/src")

# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# SOURCES
# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

set(SOLUTION_SOURCES
  "${SOLUTION_SOURCES_DIR}/native-lib.cpp"
)

# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# BUILD
# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

# Add SHARED Library Object
add_library(hexagonex_android SHARED ${SOLUTION_SOURCES})

# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
# LINK
# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

target_link_libraries(hexagonex_android
  android
  log
)

# = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = =
