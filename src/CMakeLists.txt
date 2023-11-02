cmake_minimum_required(VERSION 3.13)
include(../pico_sdk_import.cmake)
project(magic C CXX ASM)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

set(CMAKE_BUILD_TYPE Debug)
set(PICO_BOARD pico_w)

pico_sdk_init()

add_executable(magic
main.c
)

pico_enable_stdio_usb(magic 1)
pico_enable_stdio_uart(magic 0)

pico_add_extra_outputs(magic)

target_link_libraries(magic pico_stdlib)
