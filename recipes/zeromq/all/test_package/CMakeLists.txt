cmake_minimum_required(VERSION 3.14)
project(test_package)

set(CMAKE_VERBOSE_MAKEFILE TRUE)

include("${CMAKE_BINARY_DIR}/conanbuildinfo.cmake")
conan_basic_setup()

find_package(ZeroMQ REQUIRED)

add_executable(${PROJECT_NAME} test_package.cpp)
target_link_libraries(${PROJECT_NAME} ZeroMQ::ZeroMQ)
