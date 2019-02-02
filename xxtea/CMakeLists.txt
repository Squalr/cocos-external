cmake_minimum_required(VERSION 3.8 FATAL_ERROR)
project(xxtea VERSION 9999 LANGUAGES CXX)

add_library(xxtea STATIC xxtea.cpp)
add_library(xxtea::xxtea ALIAS xxtea)

set_target_properties(xxtea PROPERTIES
    POSITION_INDEPENDENT_CODE ON
)

target_compile_features(xxtea PUBLIC cxx_std_11 c_std_99)

target_include_directories(xxtea PUBLIC ${PROJECT_SOURCE_DIR})
