cmake_minimum_required(VERSION 2.8)
project(NOISY8)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++14")

# Set module path
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake_modules/")
# TO DO: Set SDL2 Root Directory. Similar to this:
# set(SFML_ROOT "${CMAKE_SOURCE_DIR}/libs/SFML-2.4.2")
# Look up SDL2 and add the include directory to our include path
find_package(SDL2 REQUIRED)
include_directories(${SDL2_INCLUDE_DIR})

# Set an output directory for our binaries
set(BIN_DIR ${CMAKE_SOURCE_DIR}/bin)

add_executable(NOISY8 test.cpp)
target_link_libraries(NOISY8 ${SDL2_LIBRARY})
install(TARGETS NOISY8 RUNTIME DESTINATION ${BIN_DIR})