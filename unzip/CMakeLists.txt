cmake_minimum_required(VERSION 3.8 FATAL_ERROR)
project(unzip VERSION 9999 LANGUAGES CXX)

find_package(ZLIB REQUIRED)

add_library(unzip STATIC
    ioapi.cpp
    ioapi_mem.cpp
    unzip.cpp
)

add_library(unzip::unzip ALIAS unzip)

target_link_libraries(unzip PRIVATE ZLIB::ZLIB)
target_include_directories(unzip PUBLIC ${PROJECT_SOURCE_DIR})

# BAD HORRIBLE EVIL DO NOT INCLUDE CROSS-PROJECT HEADERS
target_include_directories(unzip PRIVATE
    ${PROJECT_SOURCE_DIR}/../../cocos
)
