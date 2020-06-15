cmake_minimum_required(VERSION 3.3)
project(u8g2_sw_spi)

add_executable(u8g2_sw_spi ./u8g2_4wire_sw_spi.c)

target_include_directories(u8g2_sw_spi PRIVATE ../../include)
target_link_libraries(u8g2_sw_spi PUBLIC U8G2_linux_lib)