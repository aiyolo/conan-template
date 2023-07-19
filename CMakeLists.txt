cmake_minimum_required(VERSION 3.17)

project(conan-template LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

find_package(boost REQUIRED COMPONETNTS filesystem)
add_executable(conan-template
  main.cpp
)

target_link_libraries(conan-template PRIVATE Boost::filesystem)
