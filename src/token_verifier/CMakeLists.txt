cmake_minimum_required(VERSION 3.10)

project(trustauthority_token_verifier)

include_directories(../connector)

add_library(${PROJECT_NAME}
    token_verifier.c
    util.c
)

target_include_directories(${PROJECT_NAME}
    PUBLIC
    "$<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>"
    PRIVATE
    ../../include
)

target_include_directories (${PROJECT_NAME} PRIVATE
    ${SSL_LIBRARY_INCLUDE_DIR}
    ${jansson_SOURCE_DIR}/src
    ${jansson_SOURCE_DIR}/android
    ${CMAKE_CURRENT_BINARY_DIR}
)

target_link_libraries(${PROJECT_NAME} PUBLIC trustauthority_connector)
