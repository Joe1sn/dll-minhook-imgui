cmake_minimum_required(VERSION 3.11)
project(minhook)

set(MINHOOK_SOURCES
    buffer.c
    hook.c
    trampoline.c
    hde/hde32.c
    hde/hde64.c
    )

set(MINHOOK_INCLUDE
    buffer.h
    trampoline.h
    hde/hde32.h
    hde/hde64.h
    hde/pstdint.h
    hde/table32.h
    hde/table64.h
    )

add_library(${PROJECT_NAME}  STATIC
    ${MINHOOK_SOURCES}
    ${MINHOOK_INCLUDE}
)

target_include_directories(${PROJECT_NAME}  PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}
)