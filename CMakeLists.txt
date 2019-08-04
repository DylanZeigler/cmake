cmake_minimum_required (VERSION 2.6)
project (cmake_Tutorial)

# The version number
set (Tutorial_VERSION_MAJOR 1)
set (Tutorial_VERSION_MINOR 0)

# configure a header file to pass some of the CMake settings
# to the source code
configure_file (
        "${PROJECT_SOURCE_DIR}/cmake_tutorialconfig.h.in"
        "${PROJECT_BINARY_DIR}/cmake_tutorialconfig.h"
)

# add the binary tree to the search path for include files
# so that we will find cmake_tutorialconfig.h
include_directories("${PROJECT_BINARY_DIR}")

# add the executable
add_executable (cmake_Tutorial cmake_tutorial.cxx)