cmake_minimum_required(VERSION 3.29)

project(SystemPrograming_Lab2)

set(CMAKE_CXX_STANDARD 20)

add_library(calculator STATIC src/calculator.cpp)

target_include_directories(calculator PUBLIC ${PROJECT_SOURCE_DIR}/include)

add_executable(SystemPrograming_Lab2 src/main.cpp)

target_link_libraries(SystemPrograming_Lab2 calculator)

file(READ "${CMAKE_SOURCE_DIR}/rules.ninja" RULES)

set(CMAKE_NINJA_GENERATOR ${RULES})
