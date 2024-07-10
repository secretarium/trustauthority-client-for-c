cmake_minimum_required(VERSION 3.10)

project(trustauthority_token_provider)

add_library(${PROJECT_NAME}
    token_provider.c
)

target_include_directories(${PROJECT_NAME}
    PUBLIC
    "$<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>"
    PRIVATE
    ../../include
)

target_link_libraries(${PROJECT_NAME} PUBLIC trustauthority_connector)
