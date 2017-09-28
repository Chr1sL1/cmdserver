cmake_minimum_required(VERSION 3.5)
project(cmdserver)

include_directories(../syslib/inc)
aux_source_directory(. src_list)

set (CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -std=gnu11 -Wint-to-pointer-cast -Wpointer-to-int-cast")

add_compile_options(-g)
#add_compile_options(-O2)

set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -finline-functions")

add_executable(cmdserver ${src_list})
target_link_libraries(cmdserver syslib)
target_link_libraries(cmdserver rt)

