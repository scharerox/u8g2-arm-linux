cmake_minimum_required(VERSION 3.3)
project(U8G2_linux)

set(src_u8g
        ./u8g2src/u8g2_bitmap.c
        ./u8g2src/u8g2_box.c
        ./u8g2src/u8g2_buffer.c
        ./u8g2src/u8g2_circle.c
        ./u8g2src/u8g2_cleardisplay.c
        ./u8g2src/u8g2_d_memory.c
        ./u8g2src/u8g2_d_setup.c
        ./u8g2src/u8g2_font.c
        ./u8g2src/u8g2_fonts.c
        ./u8g2src/u8g2_hvline.c
        ./u8g2src/u8g2_input_value.c
        ./u8g2src/u8g2_intersection.c
        ./u8g2src/u8g2_kerning.c
        ./u8g2src/u8g2_line.c
        ./u8g2src/u8g2_ll_hvline.c
        ./u8g2src/u8g2_message.c
        ./u8g2src/u8g2_polygon.c
        ./u8g2src/u8g2_selection_list.c
        ./u8g2src/u8g2_setup.c
        ./u8g2src/u8log.c
        ./u8g2src/u8log_u8g2.c
        ./u8g2src/u8log_u8x8.c
        ./u8g2src/u8x8_8x8.c
        ./u8g2src/u8x8_byte.c
        ./u8g2src/u8x8_cad.c
        ./u8g2src/u8x8_d_a2printer.c
        ./u8g2src/u8x8_d_il3820_296x128.c
        ./u8g2src/u8x8_d_ist3020.c
        ./u8g2src/u8x8_d_ks0108.c
        ./u8g2src/u8x8_d_lc7981.c
        ./u8g2src/u8x8_d_ld7032_60x32.c
        ./u8g2src/u8x8_d_ls013b7dh03.c
        ./u8g2src/u8x8_d_max7219.c
        ./u8g2src/u8x8_d_pcd8544_84x48.c
        ./u8g2src/u8x8_d_pcf8812.c
        ./u8g2src/u8x8_d_pcf8814_hx1230.c
        ./u8g2src/u8x8_d_sbn1661.c
        ./u8g2src/u8x8_d_sed1330.c
        ./u8g2src/u8x8_d_sh1106_64x32.c
        ./u8g2src/u8x8_d_sh1106_72x40.c
        ./u8g2src/u8x8_d_sh1107.c
        ./u8g2src/u8x8_d_sh1108.c
        ./u8g2src/u8x8_d_sh1122.c
        ./u8g2src/u8x8_d_ssd1305.c
        ./u8g2src/u8x8_d_ssd1306_48x64.c
        )

file(GLOB SRC_U8G2_FILES ${PROJECT_SOURCE_DIR}/u8g2src/*.c)

file(GLOB SRC_PORT_FILES ${PROJECT_SOURCE_DIR}/port/*.c)

file(GLOB SRC_DEV_FILES ${PROJECT_SOURCE_DIR}/drivers/*.c)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -W -Wall")

add_library(U8G2_linux_lib ${SRC_U8G2_FILES} ${SRC_DEV_FILES} ${SRC_PORT_FILES})

target_include_directories(U8G2_linux_lib PUBLIC ./u8g2src ./port ./drivers)

# Examples
option(BUILD_EXAMPLES "Build examples" OFF) #OFF by default
if(BUILD_EXAMPLES)
    add_subdirectory(examples)
endif(BUILD_EXAMPLES)