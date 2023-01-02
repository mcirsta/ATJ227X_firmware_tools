cmake_minimum_required(VERSION 3.16)
project(atjboottool LANGUAGES C)

set(CMAKE_C_STANDARD 17)
set(CMAKE_C_STANDARD_REQUIRED ON)



add_compile_options($<$<CONFIG:DEBUG>:-fsanitize=address>
        $<$<NOT:$<CONFIG:DEBUG>>:-O3>)
add_link_options($<$<CONFIG:DEBUG>:-fsanitize=address>)


set(ATJ_TOOL_SOURCES
    atjboottool.c
    fwu.c
    misc.c)

add_executable(atjboottool ${ATJ_TOOL_SOURCES})
