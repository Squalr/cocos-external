cmake_minimum_required(VERSION 3.8 FATAL_ERROR)
project(clipper VERSION 6.1.3 LANGUAGES CXX)

add_library(clipper STATIC clipper.cpp)
add_library(clipper::clipper ALIAS clipper)

set_target_properties(clipper PROPERTIES
    POSITION_INDEPENDENT_CODE ON
)

target_compile_features(clipper PUBLIC cxx_std_11 c_std_99)

target_include_directories(clipper PUBLIC ${PROJECT_SOURCE_DIR})
