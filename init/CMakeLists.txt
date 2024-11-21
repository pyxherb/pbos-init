find_package(PbOSCommon REQUIRED)

file(GLOB SRC *.c *.h *.S)
add_executable(pbinit ${SRC})
target_link_options(pbinit PRIVATE "-T${PROJECT_SOURCE_DIR}/scripts/ld/${CMAKE_SYSTEM_PROCESSOR}/init.lds")
set_target_properties(pbinit PROPERTIES RUNTIME_OUTPUT_DIRECTORY ${PROJECT_BINARY_DIR})

target_include_directories(pbinit SYSTEM BEFORE PRIVATE ${FreeSTDC_INCLUDE_DIR})
target_include_directories(pbinit PUBLIC ${PbOSCommon_INCLUDE_DIR})

target_link_libraries(pbinit freestdc)
