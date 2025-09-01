cmake_minimum_required(VERSION 3.28)
project(ProgAlap)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

include_directories(include)

file(GLOB_RECURSE SOURCES "src/*.c" "src/*.cpp")

add_compile_options(-Wall -Wextra -pedantic -Werror)
add_executable(main ${SOURCES})