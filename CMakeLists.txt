cmake_minimum_required(VERSION 3.15)

set(EMBFMT_TARGET embfmt)

if (EMBFMT_TARGET_TAG) 
    set(EMBFMT_TARGET "${EMBFMT_TARGET}_${EMBFMT_TARGET_TAG}")
    message("Custom embfmt target: ${EMBFMT_TARGET}")
endif()

set(EMBFMT_SRC
    embformat.c
    embformat.h
)

set(EMBFMT_INCLUDE_PATH ${CMAKE_CURRENT_LIST_DIR} PARENT_SCOPE)

add_library(${EMBFMT_TARGET} STATIC ${EMBFMT_SRC})
target_include_directories(${EMBFMT_TARGET} PRIVATE ${EMBFMT_INCLUDES})
target_compile_options(${EMBFMT_TARGET} PRIVATE ${EMBFMT_CPU_PARAMS})
target_compile_definitions(${EMBFMT_TARGET} PRIVATE ${EMBFMT_COMPILE_DEFS})


