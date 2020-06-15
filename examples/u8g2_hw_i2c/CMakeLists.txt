cmake_minimum_required(VERSION 3.3)
project(u8g2_hw_i2c)

add_executable(u8g2_hw_i2c ./u8g2_hw_i2c.c)

target_include_directories(u8g2_hw_i2c PUBLIC ../../port ../../u8g2src ../../drivers)
target_link_libraries(u8g2_hw_i2c PUBLIC U8G2_linux_lib)