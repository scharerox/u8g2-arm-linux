cmake_minimum_required(VERSION 3.3)
project(U8G2_linux)

file(GLOB SRC_FILES ${PROJECT_SOURCE_DIR}/src/*.c ${PROJECT_SOURCE_DIR}/src/driver/*.c ${PROJECT_SOURCE_DIR}/src/u8g2/*.c)


set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -W -Wall")

add_library(U8G2_linux_lib ${SRC_FILES})

target_include_directories(U8G2_linux_lib PUBLIC ./include ./include/driver)

# Examples
option(BUILD_EXAMPLES "Build examples" OFF) #OFF by default
if(BUILD_EXAMPLES)
    add_subdirectory(examples)
endif(BUILD_EXAMPLES)