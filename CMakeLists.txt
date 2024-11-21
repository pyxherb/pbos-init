cmake_minimum_required(VERSION 3.23)
project(PbOSInit)

find_package(FreeSTDC REQUIRED)

add_freestdc_build(freestdc ${CMAKE_CURRENT_BINARY_DIR}/freestdc)

add_subdirectory("init")
