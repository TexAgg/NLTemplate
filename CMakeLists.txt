CMAKE_MINIMUM_REQUIRED(VERSION 2.8.3)
project(NLTemplate)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -g -std=c++11")

enable_testing()

add_subdirectory(${PROJECT_SOURCE_DIR}/NLTemplate)