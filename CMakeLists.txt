cmake_minimum_required(VERSION 3.13)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

include(pico_sdk_import.cmake)

project(comm C CXX ASM)

pico_sdk_init()

add_executable(comm comm.c )

pico_set_program_name(comm "comm")
pico_set_program_version(comm "0.1")

pico_enable_stdio_uart(comm 1)
pico_enable_stdio_usb(comm 0)

target_link_libraries(comm
	pico_stdlib)

pico_add_extra_outputs(comm)
