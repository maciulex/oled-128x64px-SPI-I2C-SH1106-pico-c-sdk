cmake_minimum_required(VERSION 3.12)
include(pico_sdk_import.cmake)
project(oled C CXX ASM)

pico_sdk_init()

add_executable(oled
        main.cpp
    )

pico_enable_stdio_usb(oled 1)
pico_enable_stdio_uart(oled 0)

target_link_libraries(oled pico_stdlib hardware_spi) #hardware_spi hardware_i2c
pico_add_extra_outputs(oled)