cmake_minimum_required(VERSION 3.6)
project(chibicc C)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${CMAKE_CURRENT_SOURCE_DIR}/bin")
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY "${CMAKE_CURRENT_SOURCE_DIR}/bin")

set(CMAKE_C_STANDARD 11)

# Set compiler flags
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -g -fno-common -Wall -Wno-switch")

# Collect all .c source files in the current directory
file(GLOB SRCS "*.c")

# Create an executable target from the source files
add_executable(chibicc ${SRCS})

# Specify dependencies (if any header files are required)
target_include_directories(chibicc PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})
