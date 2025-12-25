cmake_minimum_required(VERSION 3.13)

# Import Pico SDK
include($ENV{PICO_SDK_PATH}/external/pico_sdk_import.cmake)

# Prosjektnavn og språk
project(pico_project C CXX)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 20)

# Initialiser Pico SDK
pico_sdk_init()

add_executable(pico_project
        main.cpp
)

target_link_libraries(pico_project pico_stdlib)

#hvordan printf/stdio skal fungere
pico_enable_stdio_usb(pico_project 1)
pico_enable_stdio_uart(pico_project 0)

# Generer .uf2, .bin, .elf
pico_add_extra_outputs(pico_project)
